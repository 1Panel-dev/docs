## 1 Environment Requirements

!!! note ""
    **Ensure your system meets the following requirements before installation:**

    - Operating System: Supports mainstream Linux distributions (Debian/RedHat-based, including domestic OSes)
    - Server Architecture: x86_64, aarch64, armv7l, ppc64le, s390x, riscv64
    - Memory: Recommended available memory ≥ 1GB
    - Browser: Use modern browsers such as Chrome, Firefox, IE10+, Edge
    - **Internet access is required**

## 2 Installation and Deployment

!!! note ""
    GitHub release link: https://github.com/1Panel-dev/1Panel/releases

!!! note ""

    Run the following installation script and follow the command-line prompts to complete installation:
    ```bash
    bash -c "$(curl -sSL https://resource.1panel.pro/quick_start.sh)"
    ```

!!! note ""
    After successful installation, the console will print panel access information. Access 1Panel via browser:
    
    ```
    http://<Server Public IP>:<Target Port>/<Security Entrance>
    ```
    
    - **For cloud servers, open the target port in the security group**
    - **After SSH login to the 1Panel server, run `1pctl user-info` to get the security entrance**

!!! note ""
    After installation, use the [1pctl](cli.md) command-line tool to maintain 1Panel
