# 使用 1Panel 可视化安装 Nextcloud

!!! note ""
     **Nextcloud** 是一款开源的自托管云存储和协作平台，它提供了一系列功能，旨在帮助您管理和共享文件、日历、联系人、任务等，同时保护您的数据隐私。

## 1. 打开应用商店

!!! note ""
    进入 1Panel 控制台后，点击左侧菜单的 **「应用商店」**。

![image-20251016110510084](../../img/app/appstores.png)

## 2. 搜索 Nextcloud 并安装

!!! note ""
    在右上角搜索框输入 **Nextcloud**，点击应用卡片进入详情页，选择 **安装**。

![image-20251017113630514](../../img/app/nextcloud.png)

## 3. 配置安装参数

!!! note ""
     你可以根据需要配置

    - **名称** (输入框内可自定义应用名称，默认为 nextcloud)
    - **版本** (下拉选择所需的 Nextcloud 版本)
    - **端口** (应用的访问端口，默认为 40069)
    - **时区** (设置容器运行时区，默认为 Asia/Shanghai)
    - **端口外部访问** (开启后，将允许从外部网络访问此应用端口)
    
    确认设置无误后，点击 **确认** 按钮开始安装。


![image-20251017133618550](../../img/app/nextcloud_install.png)

!!! note ""
     等待安装完成即可

## 4. 访问 Nextcloud 服务

!!! note ""
     默认端口为 443，因此初次访问时，需要在浏览器地址栏使用 `https://IP:端口` 的格式

![image-20251017134623486](../../img/app/nextcloud_view.png)

!!! note ""
     可以在 **容器** 页面点击 **编辑** 修改端口配置

![image-20251017134941753](../../img/app/nextcloud_port.png)

!!! note ""
     修改为 80 端口即可

![image-20251017135035543](../../img/app/nextcloud_portchange.png)