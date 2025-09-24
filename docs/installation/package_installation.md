## 1. 特点

!!! note "完全独立运行"
    - 离线版集成 1Panel 社区版的全部功能，可在无外网环境中独立运行。  
    - 尤其适用于企业内网、离线机房及涉密环境的部署场景。

!!! note "应用商店支持"
    - 离线包中已预置常用应用的镜像，并会在安装完成后自动导入系统。 
        - **OpenResty 版本**：`1.27.1.2-2-3-focal`  
        - **MySQL 版本**：`8.4.6`、`8.0.43`、`5.7.44`、`5.6.51`
    - 除了内置镜像，用户还可以通过导入外部镜像的方式来安装其他应用。
        - 其他应用需要用户手动导入镜像后才能使用，导入教程参考 [导入应用镜像](#6)。
    - 镜像一旦导入成功，即可在 1Panel 应用商店中显示并安装，灵活性高。·

!!! note "自动安装 Docker"
    - 安装过程中若检测到系统未安装 Docker，脚本将自动完成 Docker 的安装。

## 2. 环境要求

!!! note ""
    **安装前请确认系统满足以下条件：**

    - 操作系统：支持主流 Linux 发行版（基于 Debian/RedHat，包括国产操作系统）
    - 服务器架构：x86_64
    - 内存：建议可用内存不小于 1GB
    - 浏览器：Chrome、FireFox、IE10+、Edge 等现代浏览器

## 3. 下载离线包

!!! note ""
    请下载最新版 1Panel 离线包，并上传至目标服务器的 `/tmp` 目录。

    > **下载地址**：离线包下载链接将在版本上线后第一时间公布，请关注后续更新。

## 4. 安装部署

### 4.1 解压离线包

!!! note ""
    使用 root 用户登录目标服务器，执行以下命令：

    ```bash
    cd /tmp
    # 解压离线包（请将示例文件名替换为实际名称）
    tar zxvf 1panel-v2.0.11-offline-linux-amd64.tar.gz
    ```

### 4.2 执行安装脚本

!!! note ""
    ```bash
    # 进入解压目录（请根据实际目录名替换）
    cd 1panel-v2.0.11-offline-linux-amd64
    
    # 执行安装脚本
    /bin/bash install.sh
    ```

## 5. 登录访问

!!! note ""
    安装成功后，控制台将显示面板访问信息。可通过浏览器访问：

    ```
    http://目标服务器IP地址:目标端口/安全入口
    ```

    - **如使用云服务器，请确保安全组已开放目标端口**
    - **执行 `1pctl user-info` 命令可查看安全入口（entrance）**

!!! note ""
    安装完成后，可使用 [1pctl 命令行工具](cli.md) 进行日常维护。

## 6. 导入应用镜像

!!! note ""
    如需使用其他应用（如 JumpServer），可手动导入镜像，具体步骤如下：

    1. **在可联网机器上拉取并导出镜像**：

        ```bash
        docker pull jumpserver/jms_all:v4.10.8
        docker save -o /tmp/jumpserver_4.10.8.tar jumpserver/jms_all:v4.10.8
        ```

    2. **上传镜像文件**：将 `jumpserver_4.10.8.tar` 上传至 1Panel 服务器的 `/tmp` 目录

        ```bash
        scp /tmp/jumpserver_4.10.8.tar root@<1Panel 离线服务器 IP>:/tmp/
        ```

    3. **导入镜像**：在 1Panel 服务器上执行：

        ```bash
        docker load -i /tmp/jumpserver_4.10.8.tar
        ```

    完成上述步骤后，即可在应用商店中看到 JumpServer 应用并直接安装使用。
