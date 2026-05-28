## 1 环境要求

!!! note ""
	🎉 **1Panel 企业版发布！**  1Panel 企业版是轻量级 AI 管理平台，能够帮助企业用户实现从底层硬件到智能体（Metal-to-Agent）的统一管理。 👉 [进一步了解和试用 1Panel 企业版](https://1panel.cn/enterprise.html)
   
!!! note ""
    **安装前请确保您的系统符合安装条件：**

    - 操作系统：支持主流 Linux 发行版本（基于 Debian / RedHat，包括国产操作系统）
    - 服务器架构：x86_64、aarch64、armv7l、ppc64le、s390x、riscv64
    - 内存要求：建议可用内存在 1GB 以上
    - 浏览器要求：请使用 Chrome、Firefox、IE 10+、Edge 等现代浏览器
    - **可访问互联网**
    - 如果是内网环境，推荐使用 [离线安装包](https://1panel.cn/docs/v2/installation/package_installation/) 方式进行部署

!!! note "服务器优惠"
    如果你还没有服务器，欢迎通过以下优惠链接选购。

    - 阿里云：[专属阿里云特价链接 7 折优惠](https://market.aliyun.com/common/dashi/1panel?userCode=kmemb8jp) 
    - 腾讯云：[【腾讯云】2核2G3M云服务器7.92元/月起，2000元代金券免费领](https://curl.qcloud.com/dK2muFbM)，更多云产品优惠请点击[此链接](https://curl.qcloud.com/9Ogon25Y) 

## 2 安装部署

!!! note ""
    GitHub Release 链接：https://github.com/1Panel-dev/1Panel/releases

    
!!! note ""

    执行以下安装脚本，根据命令行提示完成安装。
    ```bash
    bash -c "$(curl -sSL https://resource.fit2cloud.com/1panel/package/v2/quick_start.sh)"
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

    - **如果使用的是云服务器，请在安全组中开放对应的目标端口**
    - **ssh 登录 1Panel 服务器后，执行 `1pctl user-info` 命令可获取安全入口（entrance）**

!!! note ""
    安装成功后，可使用 [1pctl](cli.md) 命令行工具来维护 1Panel
