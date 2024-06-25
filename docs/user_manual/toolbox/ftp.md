
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
        # 开启被动端口范围 (这里需要根据实际需求调整端口范围)
        PassivePortRange 39000 40000
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
        # 与 centos 不同，这里需要在 /etc/pure-ftpd/conf 文件夹下执行下列命令，增加对应配置文件：

        # 创建 /etc/pure-ftpd/conf/PureDB 文件，内容指定路径 /etc/pure-ftpd/pureftpd.pdb
        echo '/etc/pure-ftpd/pureftpd.pdb' > /etc/pure-ftpd/conf/PureDB
        # 创建 /etc/pure-ftpd/conf/VerboseLog 文件，开启日志
        echo yes > /etc/pure-ftpd/conf/VerboseLog 
        # 创建 /etc/pure-ftpd/conf/NoAnonymous 文件，拒绝匿名登录
        echo yes > /etc/pure-ftpd/conf/NoAnonymous
        # 创建 /etc/pure-ftpd/conf/PassivePortRange 文件，开启被动端口范围 (这里需要根据实际需求调整端口范围)
        echo '39000 40000' > /etc/pure-ftpd/conf/PassivePortRange
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
    - 如果无法正常连接，可以从以下方向检查：
        - 防火墙是否开启，是否放行 Pure-FTPd 端口 ( 默认 21，可以通过 netstat -tunlp |grep pure-ftpd 或者 cat /etc/pure-ftpd/pure-ftpd.conf | grep Bind 查询)
        - 是否放行 Pure-FTPd 被动端口 ( 可以通过 cat /etc/pure-ftpd/pure-ftpd.conf | grep PassivePortRange 或者 cat /etc/pure-ftpd/conf/PassivePortRange 文件查询 )
        - 是否开启 selinux

