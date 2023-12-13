
## 1 安装

=== "RedHat / CentOS"
    !!! Abstract ""
        **1、安装 epel 源**

        ```shell
        yum install -y epel-release
        ```

        **2、安装 fail2ban**
        
        ```shell
        yum install -y fail2ban
        ```

        **3、启动 fail2ban 服务**
        
        ```shell
        systemctl start fail2ban
        ```
        
        **4、开机自启动**

        ```shell
        systemctl enable fail2ban
        ```
        
        **5、查看 fail2ban 服务状态。**

        ```shell
        systemctl status fail2ban
        ```

=== "Ubuntu / Debian"
    !!! Abstract ""
        **安装 fail2ban**
        
        ```shell
        sudo apt-get install fail2ban
        ```

        > 安装成功后，fail2ban 会默认启动。