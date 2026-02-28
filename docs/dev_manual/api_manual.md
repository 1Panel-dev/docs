This document details how to use custom Token verification to access panel APIs in third-party services.

## 1 API Configuration Instructions

After logging in, you can view all APIs by accessing the swagger address: `{host}:{port}/1panel/swagger/index.html`.

### 1.1 Custom Token Format

1Panel has designed the following custom Token format for identity authentication of API requests:

```text
Token = md5('1panel' + API-Key + UnixTimestamp)
```

Components:

- Fixed prefix: '1panel'
- API-Key: Panel API interface key
- UnixTimestamp: Current Unix timestamp (in seconds)

### 1.2 Request Header Design

Each request must carry the following two Headers:

| Header Name        | Description              |
|-------------------|--------------------------|
| 1Panel-Token      | Custom Token value       |
| 1Panel-Timestamp  | Current Unix timestamp   |

Example request header:

```bash
curl -X POST "http://{host}:{port}/api/v2/toolbox/device/base" \
-H "1Panel-Token: <1panel_token>" \
-H "1Panel-Timestamp: <current_unix_timestamp>"
```

### 1.3 Example Implementation Code

Take the Go language as an example to show the corresponding implementation code:

```go
func validateToken(c *gin.Context) error {
    panelToken := c.GetHeader("1Panel-Token")
    panelTimestamp := c.GetHeader("1Panel-Timestamp")
    systemToken := panelToken
    systemKey = ******* // Panel API key
    expectedToken := md5Sum("1panel" + systemKey + panelTimestamp)
    if systemToken != expectedToken {
        return fmt.Errorf("invalid token")
    }
    return nil
}

func md5Sum(data string) string {
    h := md5.New()
    h.Write([]byte(data))
    return hex.EncodeToString(h.Sum(nil))
}
```

## 2 Notes

- Timestamp validity: It is necessary to ensure time synchronization between the server and the client, otherwise verification will fail. It is recommended to use NTP for time synchronization.
- Whitelist usage: Add trusted IPs or IP segments to the whitelist to avoid the overhead of frequent Token verification; if you need to allow all IPs, you can configure `0.0.0.0/0` (all IPv4) and `::/0` (all IPv6).

## 3 Frequently Asked Questions

- What if the 1Panel-Token or 1Panel-Timestamp is incorrect?

  The backend will return 401 Unauthorized with the prompt "API interface key error".

- How to generate 1Panel-Token

  Please refer to the following pseudocode:

  ```javascript
  const token = md5('1panel' + clientToken + unixTimestamp);
  ```

- Why two Headers are required

  To increase the complexity of verification and enhance security at the same time.
```
