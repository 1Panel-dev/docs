## 1 环境要求

!!! Abstract ""
    **安装前请确保您的系统符合安装条件：**

    * 操作系统：支持基于 Arch Linux 的发行版本（例如：ArchLinux、EndeavourOS、GarudaLinux等）；
    * 不建议在Manjaro中安装
    * 服务器架构：x86_64、aarch64；
    * 内存要求：建议可用内存在 1GB 以上；
    * 浏览器要求：请使用 Chrome、FireFox、IE10+、Edge等现代浏览器；
    * **可访问互联网**。

## 2 安装部署

!!! Abstract ""
    AUR 链接（稳定版）: https://aur.archlinux.org/packages/1panel-bin
    AUR 链接（测试版）: https://aur.archlinux.org/packages/1panel-dev-bin

=== "通过 AUR 手动安装（请使用非root权限安装） !!! Abstract "
    !!! Abstract ""
        ```properties
        # 稳定版
        git clone https://aur.archlinux.org/1panel-bin.git 1panel
        # 测试版
        git clone https://aur.archlinux.org/1panel-dev-bin.git 1panel
        cd 1panel-bin
        makepkg -si
        ```

=== "通过 yay 安装 !!! Abstract "
    !!! Abstract""
        ```properties
        # 稳定版
        yay -S 1panel-bin
        # 测试版
        yay -S 1panel-dev-bin
        ```

=== "通过paru安装 !!! Abstract "
    !!! Abstract ""
        ```properties
        # 稳定版
        paru -S 1panel-bin
        # 测试版
        paru -S 1panel-dev-bin
        ```

!!! Abstract ""
    安装成功后，请务必在启动`1panel.service`使用以下脚本初始化1panel，否则您的密码极有可能泄漏：
    

    ```
    # 大陆服务器
    sudo sh -c "$(curl -fsSL https://gitee.com/sengedev/1panel-bin/raw/main/1panel.init)"
    # 海外服务器
    sudo sh -c "$(curl -fsSL https://raw.githubusercontent.com/sengedev/1panel-bin/main/1panel.init)"
    ```

    - **如果使用的是云服务器，请至安全组开放目标端口。**
    - **ssh 登录 1Panel 服务器后，执行 1pctl user-info 命令可获取安全入口（entrance）**

!!! Abstract ""
    
    安装成功后，可使用 [1pctl](cli.md) 命令行工具来维护 1Panel
