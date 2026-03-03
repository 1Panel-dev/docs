## 1 Installation

=== "RedHat / CentOS"
    !!! note ""
        **1. Install EPEL repository**

        ```bash
        yum install -y epel-release
        ```

        **2. Install Fail2ban**
        
        ```bash
        yum install -y fail2ban
        ```

        **3. Start Fail2ban service**
        
        ```bash
        systemctl start fail2ban
        ```
        
        **4. Enable on boot**

        ```bash
        systemctl enable fail2ban
        ```
        
        **5. Check Fail2ban status**

        ```bash
        systemctl status fail2ban
        ```

=== "Ubuntu / Debian"
    !!! note ""
        **1. Install Fail2ban**
        
        ```bash
        sudo apt-get install fail2ban
        ```

        **2. For Debian 12 and above, install rsyslog manually**

        ```bash
        sudo apt-get install rsyslog
        ```

        **3. Start Fail2ban service**
        
        ```bash
        sudo systemctl start fail2ban
        ```
        
        **4. Enable on boot**

        ```bash
        sudo systemctl enable fail2ban
        ```
        
        **5. Check Fail2ban status**

        ```bash
        sudo systemctl status fail2ban
        ```

## 2 Default Configuration

!!! note ""
    1Panel uses the following default configuration:
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
        ignoreip = 127.0.0.1/8               # Whitelist
        enabled = true
        filter = sshd
        port = 22                            # Port
        maxretry = 2                         # Maximum retry attempts
        findtime = 300                       # Detection window (seconds)
        bantime = 600                        # Ban duration (seconds). -1 = permanent ban
        action = %(action_mwl)s
        banaction = iptables-multiport       # Ban method
        logpath = /var/log/secure            # SSH login log path
        ```

## 3 Troubleshooting

!!! note ""
    - If Fail2ban was manually installed before, add the [sshd] configuration section to `jail.local` and restart the fail2ban service to avoid blacklist retrieval errors.
    - When using the `-multiport` ban method, only the configured port (e.g., 22 in default config) will be blocked.
    - Verify the availability of the target service before changing the ban method:
        - RedHat/CentOS uses Firewalld
        - Debian/Ubuntu uses UFW
    - Adjust the log path based on your OS:
        - RedHat/CentOS: `/var/log/secure`
        - Debian/Ubuntu: `/var/log/auth.log`
    - Debian 12+ deprecated rsyslog; install it manually before use.
