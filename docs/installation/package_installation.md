## 1 环境要求

!!! Abstract ""
    **安装前请确保您的系统符合安装条件：**

    * 操作系统：支持主流 Linux 发行版本（基于 Debian / RedHat，包括国产操作系统）；
    * 服务器架构：x86_64；
    * 内存要求：建议可用内存在 1GB 以上；
    * 浏览器要求：请使用 Chrome、FireFox、IE10+、Edge等现代浏览器。

## 2 下载离线包

!!! Abstract ""
    请自行下载 1Panel 最新版本的离线包，并复制到目标机器的 /tmp 目录下。
    离线包下载链接: https://community.fit2cloud.com/#/products/1panel/downloads

## 3 安装部署

### 3.1 解压离线包

!!! Abstract ""
    以 root 用户 ssh 登录到目标机器, 并执行如下命令：

    ``` 
    cd /tmp
    # 解压离线包（1panel-v1.10.0-lts-linux-amd64.tar.gz 为示例离线包名称，操作时可根据实际离线包名称替换）
    tar zxvf 1panel-v1.10.0-lts-linux-amd64.tar.gz
    ```

### 3.2 执行安装脚本

!!! Abstract ""

	```
    # 进入离线包目录（1panel-v1.10.0-lts-linux-amd64 为示例离线包目录名称，操作时可根据实际离线包名称替换）
    cd 1panel-v1.10.0-lts-linux-amd64

    # 运行安装脚本
    /bin/bash install.sh
	```

## 4 登录访问

!!! Abstract ""
    安装成功后，控制台会打印面板访问信息，可通过浏览器访问 1Panel：

    ```
    http://目标服务器 IP 地址:目标端口/安全入口
    ```

    - **如果使用的是云服务器，请至安全组开放目标端口。**
    - **ssh 登录 1Panel 服务器后，执行 1pctl user-info 命令可获取安全入口（entrance）**

!!! Abstract ""
    
    安装成功后，可使用 [1pctl](cli.md) 命令行工具来维护 1Panel
