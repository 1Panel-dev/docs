
## 1 安装

=== "RedHat / CentOS"
    !!! Abstract ""
        **1、安装 epel 源**

        ```shell
        yum install -y epel-release
        ```

        **2、安装 supervisor**
        
        ```shell
        yum install -y supervisor
        ```

        **3、启动 supervisord 服务**
        
        ```shell
        systemctl start supervisord
        ```
        
        **4、开机自启动**

        ```shell
        systemctl enable supervisord
        ```
        
        **5、查看 supervisord 服务状态。**

        ```shell
        systemctl status supervisord
        ```

=== "Ubuntu / Debian"
    !!! Abstract ""
        **安装 supervisor**
        
        ```shell
        sudo apt-get install supervisor
        ```

        > 安装成功后，supervisor 会默认启动。

## 2、使用

!!! Abstract ""
    
    supervisor 配置托管的程序，配置文件目录为：/opt/1panel/tools/supervisord/supervisor.d/*.ini。

> /opt 目录要替换为安装 1Panel 系统时自定义的目录。
