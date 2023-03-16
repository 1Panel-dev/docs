## 1 配置

!!! Abstract ""
    
    - 支持查看 Docker 运行状态，并执行重启服务等操作。
    - 配置文件默认为：/etc/docker/daemon.json。

![img.png](../../img/containers/setting.png)

!!! Abstract ""

    - 镜像加速： 国内从 DockerHub 拉取镜像有时会遇到困难，此时可以配置镜像加速器，如：
        - 科大镜像：https://docker.mirrors.ustc.edu.cn/
        - 网易：https://hub-mirror.c.163.com/
        - 阿里云：https://<你的ID>.mirror.aliyuncs.com
        - 七牛云加速器：https://reg-mirror.qiniu.com
    - 私有仓库： 搭建的私有镜像仓库，如 harber、nexus、docker-registry 等。
    - live-restore： 停止 Docker 服务是，是否停止所有容器。
    - cgroup-driver： 
    