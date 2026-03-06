## 1 Installation

=== "RedHat / CentOS"
    
    !!! note ""
        
        **1. Install EPEL repository**

        ```bash
        yum install -y epel-release
        ```
    !!! note ""
        
        **2. Install Pure-FTPd**
        
        ```bash
        yum -y install pure-ftpd
        ```

    !!! note ""
        
        **3. Modify default configuration**
        
        ```bash
        # Default config path: /etc/pure-ftpd/pure-ftpd.conf
        # Find and update these parameters:

        # Path to PureDB user database
        PureDB /etc/pure-ftpd/pureftpd.pdb
        # Enable logging
        VerboseLog yes
        # Deny anonymous login
        NoAnonymous yes
        # Enable passive port range (adjust as needed)
        PassivePortRange 39000 40000
        ```

    !!! note ""
        
        **4. Start Pure-FTPd service**
        
        ```bash
        systemctl start pure-ftpd.service
        ```
        
    !!! note ""
        
        **5. Check service status**

        ```bash
        systemctl status pure-ftpd.service
        ```

=== "Ubuntu / Debian"
    
    !!! note ""
        
        **1. Install Pure-FTPd**
        
        ```bash
        sudo apt-get install pure-ftpd
        ```

    !!! note ""
        
        **2. Modify default configuration**
        
        ```bash
        # Debian/Ubuntu use individual files under /etc/pure-ftpd/conf

        # Set PureDB path
        echo '/etc/pure-ftpd/pureftpd.pdb' > /etc/pure-ftpd/conf/PureDB
        # Enable verbose logging
        echo yes > /etc/pure-ftpd/conf/VerboseLog
        # Deny anonymous access
        echo yes > /etc/pure-ftpd/conf/NoAnonymous
        # Set passive port range
        echo '39000 40000' > /etc/pure-ftpd/conf/PassivePortRange
        ```

    !!! note ""
        
        **3. Create database symlink**
        
        ```bash
        ln -s /etc/pure-ftpd/conf/PureDB /etc/pure-ftpd/auth/50puredb
        ```

    !!! note ""
        
        **4. Start Pure-FTPd service**
        
        ```bash
        sudo systemctl start pure-ftpd.service
        ```
        
    !!! note ""
        
        **5. Check service status**

        ```bash
        sudo systemctl status pure-ftpd.service
        ```

## 2 Troubleshooting

!!! note ""
    - If Pure-FTPd was already installed, you can sync it to 1Panel using the sync button in the UI. Passwords cannot be synced and must be edited manually.
    - If you cannot connect properly, check:
        - Whether the firewall is running and allows the Pure-FTPd port (default 21). Check with:
          `netstat -tunlp | grep pure-ftpd`
          or
          `cat /etc/pure-ftpd/pure-ftpd.conf | grep Bind`
        - Whether passive ports are allowed in the firewall. Check with:
          `cat /etc/pure-ftpd/pure-ftpd.conf | grep PassivePortRange`
          or
          `cat /etc/pure-ftpd/conf/PassivePortRange`
        - Whether SELinux is enabled
