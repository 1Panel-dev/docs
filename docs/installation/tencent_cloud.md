!!! Abstract ""
    腾讯云目前已经在轻量应用服务器的应用模板中添加了 1Panel 的模板镜像，选择应用模板购买服务器即可直接使用 1Panel。

## 1 购买轻量应用服务器

购买地址：[轻量应用服务器](https://buy.cloud.tencent.com/lighthouse?blueprintType=APP_OS&blueprintOfficialId=lhbp-pjoqcja2&regionId=8&zone=ap-beijing-3&bundleId=bundle_starter_mc_med2_01&loginSet=AUTO&from=lh-console)

在应用模板中选择 `1Panel Linux 面板`，然后选择所需地域、可用区、套餐等，点击立即购买即可。

## 2 查看应用信息

服务器初始化完成之后，进入服务器详情中的 `应用管理` 页面，即可看到 1Panel 的相关信息。

![轻量应用服务器-应用管理.png](../../img/installation/轻量应用服务器-应用管理.png)

## 3 开放防火墙端口

登录 1Panel 面板前需要先在轻量应用服务器防火墙中开放 1Panel 服务端口，进入防火墙页面添加默认端口 8090 即可。

![轻量应用服务器-防火墙.png](../../img/installation/轻量应用服务器-防火墙.png)

!!! Abstract ""
    如果后续修改了 1Panel 的服务端口，同样需要在这里添加规则。

## 4 查看登录信息

点击服务器详情页面的登录按钮，可以通过腾讯云的在线终端，在浏览器中直接进入服务器命令行，在命令行中复制并执行 `sudo /opt/1panel/get-1panel-info.sh` 命令，获取 1Panel 的登录地址和初始用户名密码。

![轻量应用服务器-查看登录信息.png](../../img/installation/轻量应用服务器-查看登录信息.png)

## 5 登录 1Panel 面板

!!! Abstract ""

    - 通过上一步获取到的 http://服务器外网IP:8090/安全入口 地址，访问面板管理页面，如：http://172.16.10.1:8090/mm4h9iucdn
    - 输入帐号密码
