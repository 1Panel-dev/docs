# 云市场部署指南

!!! Abstract ""

    本指南将介绍如何通过阿里云云市场购买、部署和使用 **1Panel** 镜像，并提供购买服务器的优惠链接。

## 1 购买镜像

!!! Abstract ""

    - 1Panel 已经上架到阿里云云市场，您可以通过以下链接直接购买镜像：
    [1Panel 云市场购买链接](https://market.aliyun.com//products/56014009/cmjj00062740.html)
    
    - 您也可以自行购买阿里云服务器，并在选择镜像时搜索 **1Panel**，即可快速选择镜像进行部署。

!!! Abstract "服务器优惠"

    如果您还没有服务器，可以通过以下优惠链接购买阿里云服务器：

    - [阿里云服务器0元试用，首购低至0.9元/月起](https://www.aliyun.com/daily-act/ecs/activity_selection?userCode=j57gyupo)
    - 更多云产品优惠请点击 [此链接](https://www.aliyun.com/minisite/goods?userCode=j57gyupo)

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

# 计算巢部署指南

阿里云计算巢提供了软件与资源的一体化交付的完善基础能力，助力服务商、开发者的提升服务能力和降低运营成本。计算巢已经支持快速部署 1Panle 社区版。

## 部署流程

1. 单击[部署链接](https://computenest.console.aliyun.com/service/instance/create/default?type=user&ServiceId=service-4b2eae361ae8493d851a)，进入服务实例部署界面。
2. 选择新建ECS实例并根据界面提示配置参数，配置完成后点击下一步：确认订单。

   ![alibabacloud_computenest_deploy_1.jpg](../../img/installation/alibabacloud_computenest_deploy_1.jpg)

3. 点击立即创建，等待服务实例创建完成。

      ![alibabacloud_computenest_deploy_2.jpg](../../img/installation/alibabacloud_computenest_deploy_2.jpg)

4. 服务实例创建成功后，进入服务实例详情页。在概览页可获取1Panel面板登录信息，点击外网面板地址，登录1Panel面板。
   
      ![alibabacloud_computenest_deploy_3.jpg](../../img/installation/alibabacloud_computenest_deploy_3.jpg)
