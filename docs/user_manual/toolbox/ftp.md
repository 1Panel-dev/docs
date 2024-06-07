
## 1 安装

=== "RedHat / CentOS"
    !!! Abstract ""
        **1、安装 epel 源**

        ```shell
        yum install -y epel-release
        ```

        **2、安装 Pure-FTPd**
        
        ```shell
        yum -y install pure-ftpd
        ```

        **3、修改默认配置**
        
        ```shell
        # 默认配置位于 /etc/pure-ftpd/pure-ftpd.conf，在配置文件中找到下面几个参数进行修改：

        # 指定路径，PureDB用户数据库文件
        PureDB /etc/pure-ftpd/pureftpd.pdb
        # 开启日志
        VerboseLog yes
        # 拒绝匿名登录
        NoAnonymous yes
        ```

        **4、启动 Pure-FTPd 服务**
        
        ```shell
        systemctl start pure-ftpd.service
        ```
        
        **5、查看 Pure-FTPd 服务状态。**

        ```shell
        systemctl status pure-ftpd.service
        ```

=== "Ubuntu / Debian"
    !!! Abstract ""
        **1、安装 Pure-FTPd**
        
        ```shell
        sudo apt-get install pure-ftpd
        ```

        **2、修改默认配置**
        
        ```shell
        # 默认配置位于 /etc/pure-ftpd/pure-ftpd.conf，在配置文件中找到下面几个参数进行修改：

        # 指定路径，PureDB用户数据库文件
        PureDB /etc/pure-ftpd/pureftpd.pdb
        # 开启日志
        VerboseLog yes
        # 拒绝匿名登录
        NoAnonymous yes
        ```

        **3、建立数据库软链**
        
        ```shell
        ln -s /etc/pure-ftpd/conf/PureDB /etc/pure-ftpd/auth/50puredb
        ```

        **4、启动 Pure-FTPd 服务**
        
        ```shell
        sudo systemctl start pure-ftpd.service
        ```
        
        
        **5、查看 Pure-FTPd 服务状态。**

        ```shell
        sudo systemctl status pure-ftpd.service
        ```

## 2 故障排除

!!! Abstract ""

    - 如果之前已经安装过 Pure-FTPd，可以直接通过界面同步按钮同步到 1panel 上，但是同步过程中无法同步密码，需要在界面上手动编辑；

