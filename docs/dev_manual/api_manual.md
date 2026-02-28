This document details how to use custom Token verification to access panel interfaces in third-party services.

# 1 Interface Configuration Instructions

After logging in, you can access all APIs via the Swagger URL:
`{host}:{port}/1panel/swagger/index.html`

## 1.1 Custom Token Format

1Panel uses the following custom Token format for API request authentication:

Token = md5('1panel' + API-Key + UnixTimestamp)

Components:
- Fixed prefix: '1panel'
- API-Key: Panel API key
- UnixTimestamp: Current Unix timestamp (in seconds)

## 1.2 Request Header Design

Each request must include the following two headers:

| Header Name       | Description               |
|-------------------|---------------------------|
| 1Panel-Token      | Custom Token value        |
| 1Panel-Timestamp  | Current Unix timestamp    |

Example request header:

curl -X POST "http://{host}:{port}/api/v2/toolbox/device/base" \
-H "1Panel-Token: <1panel_token>" \
-H "1Panel-Timestamp: <current_unix_timestamp>"

## 1.3 Example Implementation Code

Using Go as an example:

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

# 2 Notes

- Timestamp validity: Ensure server and client time are synchronized; otherwise, verification will fail. NTP time synchronization is recommended.
- Whitelist usage: Add trusted IPs or IP ranges to the whitelist to reduce frequent Token verification overhead. To allow all IPs, configure `0.0.0.0/0` (all IPv4) and `::/0` (all IPv6).

# 3 Common Issues

- What if 1Panel-Token or 1Panel-Timestamp is incorrect?
The backend returns 401 Unauthorized with the message "Invalid API key".

- How to generate 1Panel-Token
See pseudocode below:

const token = md5('1panel' + clientToken + unixTimestamp);

- Why two headers are required
To increase verification complexity and enhance security.
