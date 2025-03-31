## 1 在线安装 docker 时，提示 "ERROR: Unsupported distribution 'xxx'"

![docker错误](../img/faq/docker_error.png){ width="550px" }

!!! Abstract ""
    **上图的错误是由于 docker 的在线安装脚本不支持该操作系统导致的，目前最好的解决方案就是先手动在服务器上安装并启动 Docker，然后再安装 1Panel。**

    可以尝试运行以下脚本：
    ```shell
    bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
    ```
    了解更多信息，请访问官方网站：https://linuxmirrors.cn

## 2 使用 windows 的 wsl 子系统安装失败

!!! Abstract ""
    **System has not been booted with systemd as init system (PID 1). Can't operate. Failed to connect to bus: Host is down**

![wsl 错误](../img/faq/wsl_error.jpg){ width="550px" }

!!! Abstract ""
    **上图的错误是由于 wsl 子系统不能使用 systemd 导致的启动 docker 服务失败**

    - 更新 systemd 管理，支持 systemd 后问题即可解决
    - 参考文档：[Systemd support is now available in WSL!](https://devblogs.microsoft.com/commandline/systemd-support-is-now-available-in-wsl/)

## 3 使用 Fedora 37 安装面板后打开防火墙发现面板创建的端口规则未效果

!!! Abstract ""
    **Fedora 37 默认区域不是 public 导致的，可以通过以下命令手动将默认区域设置为 public**

    ```shell
    firewall-cmd --set-default-zone=public
    ```

    ```shell
    firewall-cmd --reload
    ```
