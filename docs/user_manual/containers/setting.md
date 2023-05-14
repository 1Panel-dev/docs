## 1 配置

!!! Abstract ""
    
    - 支持查看 Docker 运行状态，并执行重启服务等操作。
    - 配置文件默认为：/etc/docker/daemon.json。

![img.png](../../img/containers/setting.png)

!!! Abstract ""

    - 镜像加速：国内访问 Docker Hub 有时会遇到困难，此时可以配置镜像加速器。国内很多云服务商都提供了加速器服务，例如：
        - [DaoCloud 加速器](https://www.daocloud.io/mirror#accelerator-doc)：https://<你的ID>.m.daocloud.io
        - [阿里云加速器](https://cr.console.aliyun.com/#/accelerator)：https://<你的ID>.mirror.aliyuncs.com
    - 私有仓库：搭建的私有镜像仓库，如 harber、nexus、docker-registry 等。
    - iptables：该设置将关闭 Docker 对 iptables 规则的自动配置，这可能会导致容器无法与外部网络通信。
    - live-restore：停止 Docker 服务是，是否停止所有容器。
    - cgroup-driver：默认情况下使用的 Cgroup Driver 为 cgroupfs。
