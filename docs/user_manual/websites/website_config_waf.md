## 网站安全设置
!!! Abstract ""

    配置网站的 WAF 

### CC 防护

!!! Abstract ""

    配置 CC 防护，填写以下信息：

    - 周期：CC 防护的检测周期
    - 频率：CC 防护的频率设置

    例如周期 60 频率 100 代表 60 秒内累计请求同一URL超过 100 次,触发CC防御,封锁此IP
    

![img.png](../../img/websites/waf_cc.png)

### IP 白名单

!!! Abstract ""

    设置访问网站的 IP 白名单

![img.png](../../img/websites/ip_white.png)

### IP 黑名单

!!! Abstract ""

    设置禁止访问网站的 IP 黑名单

![img.png](../../img/websites/ip_black.png)

### URL 白名单

!!! Abstract ""

    设置访问网站的 URL 白名单

![img.png](../../img/websites/url_white.png)

### URL 黑名单

!!! Abstract ""

    设置禁止访问网站的 URL 黑名单

![img.png](../../img/websites/url_black.png)

### Cookie 黑名单

    设置禁止 Cookie 中携带的数据黑名单

![img.png](../../img/websites/cookie_black.png)

### Get 参数校验
    
    设置禁止 Get 请求中携带的参数

![img.png](../../img/websites/get_check.png)

### POST 参数校验

    设置禁止 POST 请求中携带的参数

![img.png](../../img/websites/post_check.png)


### 文件扩展名黑名单
    
    这是禁止上传的文件类型

![img.png](../../img/websites/ext_block.png)