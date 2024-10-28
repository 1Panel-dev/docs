# 云市场部署指南

!!! Abstract ""

    本指南将介绍如何通过阿里云云市场购买、部署和使用 **1Panel** 镜像，并提供购买服务器的优惠链接。

## 1 购买镜像

!!! Abstract ""

    - 1Panel 已经上架到阿里云云市场，您可以通过以下链接直接购买镜像：
    [1Panel 云市场购买链接](https://market.aliyun.com/products/53690006/cmjj00062740.html?userCode=kmemb8jp)
    
    - 您也可以自行购买阿里云服务器，并在选择镜像时搜索 **1Panel**，即可快速选择镜像进行部署。

!!! Abstract "服务器优惠"

    如果您还没有服务器，可以通过以下优惠链接购买阿里云服务器：

    - [1Panel 专属阿里云特价链接 5.5 折优惠！](https://market.aliyun.com/common/dashi/1panel?userCode=kmemb8jp)

## 2 开放端口

!!! Abstract ""

    - 为了确保外部能够正常访问 1Panel 服务，您需要在阿里云服务器的安全组规则中开放 `8080` 端口。

    - 具体的开放步骤可以参考阿里云的 [端口放行教程](https://help.aliyun.com/document_detail/25471.html)。

## 3. 使用步骤

### 3.1 获取面板用户信息

!!! abstract ""
    
    - 执行命令 `1pctl user-info` 来获取默认的用户信息。
    - 输入命令并按回车，即可查看面板的用户名和密码。

### 3.2 访问面板

!!! abstract ""

    - 通过以下格式的 URL 访问面板管理页面：`http://服务器外网IP:8090/安全入口`。例如：`http://172.16.10.1:8090/mm4h9iucdn`
    - 在登录页面中输入获取的默认帐号和密码。

### 3.3 面板设置

!!! abstract ""

    - 建议首次登录后立即修改默认的帐号和密码，以确保系统安全。
    - 完成设置后，您可以开始使用面板进行管理和操作。