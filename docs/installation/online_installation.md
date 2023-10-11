## 1 环境要求

!!! Abstract ""
    **安装前请确保您的系统符合安装条件：**

    * 操作系统：支持主流 Linux 发行版本（基于 Debian / RedHat，包括国产操作系统）；
    * 服务器架构：x86_64、aarch64、armv7l、ppc64le、s390x；
    * 内存要求：建议可用内存在 1GB 以上；
    * 浏览器要求：请使用 Chrome、FireFox、IE10+、Edge等现代浏览器；
    * **可访问互联网**。

!!! info "服务器优惠"
    如果你还没有服务器，欢迎在[此页面选购](https://www.aliyun.com/daily-act/ecs/activity_selection?userCode=j57gyupo)，阿里云服务器0元试用，首购低至0.9元/月起。

    [点此查看更多云产品优惠](https://www.aliyun.com/minisite/goods?userCode=j57gyupo)。

## 2 安装部署

!!! Abstract ""
    GitHub release 链接: https://github.com/1Panel-dev/1Panel/releases  

=== "RedHat / CentOS"
    !!! Abstract ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sh quick_start.sh
        ```

=== "Ubuntu"
    !!! Abstract ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sudo bash quick_start.sh
        ```

=== "Debian"
    !!! Abstract ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && bash quick_start.sh
        ```

!!! Abstract ""
    安装成功后，控制台会打印面板访问信息，可通过浏览器访问 1Panel：

    ```
    http://目标服务器 IP 地址:目标端口/安全入口
    ```

    - **如果使用的是云服务器，请至安全组开放目标端口。**
    - **ssh 登录 1Panel 服务器后，执行 1pctl user-info 命令可获取安全入口（entrance）**

!!! Abstract ""
    
    安装成功后，可使用 [1pctl](cli.md) 命令行工具来维护 1Panel
