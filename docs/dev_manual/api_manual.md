
!!! note ""
本文档详细介绍了如何在三方服务中使用自定义 Token 的验证来访问面板接口。

## 1 接口配置说明

!!! note ""
    
    登录后，可通过访问 swagger 访问地址：`{host}:{port}/1panel/swagger/index.html` 查看所有 API。

### 1.1 自定义 Token 格式

!!! note ""

    1Panel 设计了以下自定义 Token 格式，用于接口请求的身份验证：

    ```text
    Token = md5('1panel' + API-Key + UnixTimestamp)
    ```

    组成部分：

    - 固定前缀: '1panel'
    - API-Key: 面板 API 接口密钥
    - UnixTimestamp: 当前的时间戳（秒级）

### 1.2  请求 Header 设计

!!! note ""

    每次请求必须携带以下两个 Header：
    
    | Header 名称        | 说明              |
    |------------------|--------------------|
    | 1Panel-Token     | 自定义的 Token 值    |
    | 1Panel-Timestamp | 当前时间戳           |

    示例请求头：
    
    ```bash
    curl -X POST "http://{host}:{port}/api/v2/toolbox/device/base" \
    -H "1Panel-Token: <1panel_token>" \
    -H "1Panel-Timestamp: <current_unix_timestamp>"
    ```

### 1.3 示例实现代码

!!! note ""
    以 go 语言为例，展示对应的实现代码：

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

## 2 注意事项

!!! note ""

    - 时间戳的有效性:需要确保服务器与客户端时间同步，否则会导致验证失败。建议使用 NTP 同步时间
    - 白名单使用:将可信任的 IP 或 IP 段加入白名单，避免频繁 Token 验证的开销；如需放行所有 IP ，可以配置 ，`0.0.0.0/0`（所有 IPv4），`::/0`（所有 IPv6）

## 3 常见问题

!!! note ""
    
    - 如果 1Panel-Token 或 1Panel-Timestamp 错误怎么办

        后台将返回 401 Unauthorized，并提示 "API 接口密钥错误"。

    - 如何生成 1Panel-Token
    
        请参考以下伪代码：
    
        ```javascript
        const token = md5('1panel' + clientToken + unixTimestamp);
        ```

    - 为什么需要两个 Header
    
        提高验证的复杂度，同时增强安全性。

