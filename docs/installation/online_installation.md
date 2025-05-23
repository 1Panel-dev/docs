## 1 环境要求

!!! note ""
    **安装前请确保您的系统符合安装条件：**

    - 操作系统：支持主流 Linux 发行版本（基于 Debian / RedHat，包括国产操作系统）；
    - 服务器架构：x86_64、aarch64、armv7l、ppc64le、s390x；
    - 内存要求：建议可用内存在 1GB 以上；
    - 浏览器要求：请使用 Chrome、FireFox、IE10+、Edge等现代浏览器；
    - **可访问互联网**。

!!! note "服务器优惠"
    如果你还没有服务器，欢迎通过以下优惠链接选购。

    - 阿里云：[专属阿里云特价链接 5.5 折优惠](https://market.aliyun.com/common/dashi/1panel?userCode=kmemb8jp)；
    - 腾讯云：[【腾讯云】2核2G3M云服务器7.92元/月起，2000元代金券免费领](https://curl.qcloud.com/dK2muFbM)，更多云产品优惠请点击[此链接](https://curl.qcloud.com/9Ogon25Y)；

## 2 安装部署

!!! note ""
    GitHub release 链接: https://github.com/1Panel-dev/1Panel/releases

=== "RedHat / CentOS"
    !!! note ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sh quick_start.sh
        ```

=== "Ubuntu"
    !!! note ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sudo bash quick_start.sh
        ```

=== "Debian"
    !!! note ""
        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && bash quick_start.sh
        ```

=== "openEuler / 其他"
    !!! note ""
        第一步：安装 docker

        ```properties
        bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
        ```

        第二步：安装 1Panel

        ```properties
        curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sh quick_start.sh
        ```

!!! note ""
    如果遇到 Docker 安装失败等问题，可以尝试运行以下脚本：

    ```bash
    bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
    ```

    了解更多信息，请访问官方网站：https://linuxmirrors.cn

!!! note ""
    安装成功后，控制台会打印面板访问信息，可通过浏览器访问 1Panel：

    ```
    http://目标服务器 IP 地址:目标端口/安全入口
    ```

    - **如果使用的是云服务器，请至安全组开放目标端口。**
    - **ssh 登录 1Panel 服务器后，执行 1pctl user-info 命令可获取安全入口（entrance）**

!!! note ""
    安装成功后，可使用 [1pctl](cli.md) 命令行工具来维护 1Panel
