## API 接口配置与使用指南

本文档详细介绍了如何在三方服务中使用自定义 Token 的验证来访问面板接口。

### 以下内容已通过 Swagger 进行验证
面板 swagger 访问地址：`{host}:{port}/1panel/swagger/index.html`

### 自定义 Token 格式

我们设计了以下自定义 Token 格式，用于接口请求的身份验证：

```text
Token = md5('1panel' + API-Key + UnixTimestamp)
```
组成部分：

- 固定前缀: '1panel'
- API-Key: 面板 API 接口密钥
- UnixTimestamp: 当前的时间戳（秒级）

### 请求 Header 设计

每次请求必须携带以下两个 Header：

| Header 名称        | 说明              |
|------------------|--------------------|
| 1Panel-Token     | 自定义的 Token 值    |
| 1Panel-Timestamp | 当前时间戳           |

### 示例请求头：
```shell
curl -X GET "http://localhost:4004/api/v1/dashboard/current" \
-H "1Panel-Token: <1panel_token>" \
-H "1Panel-Timestamp: <current_unix_timestamp>"
```

### 示例实现代码(go)

```go
func validateToken(c *gin.Context) error {
    panelToken := c.GetHeader("1Panel-Token")
    panelTimestamp := c.GetHeader("1Panel-Timestamp")
    systemToken := panelToken
    systemKey = ******* // 面板 API 密钥
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

## 注意事项

1.	时间戳的有效性:   
需要确保服务器与客户端时间同步，否则会导致验证失败。建议使用 NTP 同步时间。
2.	白名单使用:  
将可信任的 IP 或 IP 段加入白名单，避免频繁 Token 验证的开销；如需放行所有 IP ，可以配置 `0.0.0.0`。

## 常见问题

1.	Q: 如果 1Panel-Token或1Panel-Timestamp 错误怎么办？  
    A: 返回 401 Unauthorized，提示 "API 接口密钥错误"。  
2.	Q: 如何生成 1Panel-Token？  
    A: 参考以下伪代码：
```javascript
const token = md5('1panel' + clientToken + unixTimestamp);
```
3. Q: 为什么需要两个 Header？  
   A: 提高验证的复杂度，同时增强安全性。


## 结语

通过上述方式可以实现一个安全、高效的 Token 验证系统。如果有任何问题，请参考具体代码实现或联系我们获取支持。