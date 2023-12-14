
## 1 安装

=== "RedHat / CentOS"
    !!! Abstract ""
        **1、安装 epel 源**

        ```shell
        yum install -y epel-release
        ```

        **2、安装 Fail2ban**
        
        ```shell
        yum install -y fail2ban
        ```

        **3、启动 Fail2ban 服务**
        
        ```shell
        systemctl start fail2ban
        ```
        
        **4、开机自启动**

        ```shell
        systemctl enable fail2ban
        ```
        
        **5、查看 Fail2ban 服务状态。**

        ```shell
        systemctl status fail2ban
        ```

=== "Ubuntu / Debian"
    !!! Abstract ""
        **1、安装 Fail2ban**
        
        ```shell
        sudo apt-get install fail2ban
        ```

        **2、Debian 12 及以上的版本需要手动安装 rsyslog**

        ```shell
        sudo apt-get install rsyslog
        ```

        **3、启动 Fail2ban 服务**
        
        ```shell
        sudo systemctl start fail2ban
        ```
        
        **4、开机自启动**

        ```shell
        sudo systemctl enable fail2ban
        ```
        
        **5、查看 Fail2ban 服务状态。**

        ```shell
        sudo systemctl status fail2ban
        ```

## 2 默认配置

!!! Abstract ""

    1Panel 会默认使用以下配置：
        ```properties
        #DEFAULT-START
        [DEFAULT]
        bantime = 600
        findtime = 300
        maxretry = 5
        banaction = firewallcmd-ipset
        action = %(action_mwl)s
        #DEFAULT-END
        
        [sshd]
        ignoreip = 127.0.0.1/8               # 白名单
        enabled = true
        filter = sshd
        port = 22                            # 端口
        maxretry = 2                         # 最大尝试次数
        findtime = 300                       # 发现周期 单位s
        bantime = 600                        # 封禁时间，单位s。-1为永久封禁
        action = %(action_mwl)s
        banaction = iptables-multiport       # 禁用方式
        logpath = /var/log/secure            # SSH 登陆日志位置
        ```

## 3 故障排除

!!! Abstract ""

    - 如之前已经手动安装过 Fail2ban，需要将 [sshd] 部分的配置信息写入到 jail.local 中，重启 fail2ban 服务，否则可能出现获取黑名单报错的问题；
    - 如果选择的禁用方式为 -muliport，则在封禁时，只会禁用配置中的端口，如默认配置中的 22；
    - 如果需要修改禁用方式，需要先判读对应服务是否正常可用；
        - RedHat/CentOS 使用的是 Firewall 防火墙。
        - Debian/Ubuntu使用的是 UFW 防火墙。
    - 日志路径需要根据操作系统修改。
        - RedHat/CentOS 日志为 /var/log/secure。
        - Debian/Ubuntu 日志为 /var/log/auth.log
    - Debian 从 12 开始弃用了 rsyslog，使用时需要先自行安装；
