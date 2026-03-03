## 1 Environment Requirements

!!! note ""
    **Ensure your system meets the following requirements before installation:**

    - Operating System: Supports mainstream Linux distributions (Debian/RedHat-based, including domestic OSes)
    - Server Architecture: x86_64, aarch64, armv7l, ppc64le, s390x, riscv64
    - Memory: Recommended available memory ≥ 1GB
    - Browser: Use modern browsers such as Chrome, Firefox, IE10+, Edge
    - **Internet access is required**
    - For intranet environments, offline deployment via [offline installation package](https://1panel.cn/docs/v2/installation/package_installation/) is recommended

!!! note "Server Discounts"
    If you do not have a server yet, you can purchase one via the following discount links:

    - Alibaba Cloud: [Exclusive 30% OFF Link for 1Panel Users](https://market.aliyun.com/common/dashi/1panel?userCode=kmemb8jp)
    - Tencent Cloud: [Tencent Cloud - 2-core 2G 3M Cloud Server from ¥7.92/month, ¥2000 coupon pack free](https://curl.qcloud.com/dK2muFbM). For more cloud product discounts, click [this link](https://curl.qcloud.com/9Ogon25Y)

## 2 Installation and Deployment

!!! note ""
    GitHub release link: https://github.com/1Panel-dev/1Panel/releases

!!! note ""

    Run the following installation script and follow the command-line prompts to complete installation:
    ```bash
    bash -c "$(curl -sSL https://resource.fit2cloud.com/1panel/package/v2/quick_start.sh)"
    ```

!!! note ""
    If you encounter issues like Docker installation failure, try this alternative script:
    
    ```bash
    bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
    ```
    
    For more information, visit the official site: https://linuxmirrors.cn

!!! note ""
    After successful installation, the console will print panel access information. Access 1Panel via browser:
    
    ```
    http://<Server Public IP>:<Target Port>/<Security Entrance>
    ```
    
    - **For cloud servers, open the target port in the security group**
    - **After SSH login to the 1Panel server, run `1pctl user-info` to get the security entrance**

!!! note ""
    After installation, use the [1pctl](cli.md) command-line tool to maintain 1Panel
