# Fail2ban

## Introduction

Fail2Ban scans log files like /var/log/auth.log and bans IP addresses conducting too many failed login attempts. It does this by updating system firewall rules to reject new connections from those IP addresses, for a configurable amount of time. Fail2Ban comes out-of-the-box ready to read many standard log files, such as those for sshd and Apache, and is easily configured to read any log file of your choosing, for any error you wish.

1Panel uses Fail2Ban to reduce the rate of incorrect authentication attempts.

## Installing Fail2ban

=== "RedHat / CentOS"
    1. Install the EPEL repository
    ```shell
    yum install -y epel-release
    ```
    2. Install Fail2ban
    ```shell
    yum install -y fail2ban
    ```
    3. Start the Fail2ban service
    ```shell
    systemctl start fail2ban
    ```
    4. Enable Fail2ban to start at boot
    ```shell
    systemctl enable fail2ban
    ```
    5. Check the status of the Fail2ban service
    ```shell
    systemctl status fail2ban
    ```

=== "Ubuntu / Debian"
    1. Install Fail2ban
    ```shell
    sudo apt-get install fail2ban
    ```
    2. For Debian 12 and later versions, rsyslog needs to be installed manually
    ```shell
    sudo apt-get install rsyslog
    ```
    3. Start the Fail2ban service
    ```shell
    sudo systemctl start fail2ban
    ```
    4. Enable Fail2ban to start at boot
    ```shell
    sudo systemctl enable fail2ban
    ```
    5. Check the status of the Fail2ban service
    ```shell
    sudo systemctl status fail2ban
    ```

## Configuration

On the 1Panel console, Fail2ban configurations can be viewed and modified, enabling the management of IP lists that are either allowed or blocked.

!!! Abstract "Default Configuration"
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
        ignoreip = 127.0.0.1/8
        enabled = true
        filter = sshd
        port = 22                         
        maxretry = 2                       
        findtime = 300
        bantime = 600       
        action = %(action_mwl)s
        banaction = iptables-multiport
        logpath = /var/log/secure
        ```

## Troubleshooting

- If Fail2ban has been manually installed previously, it is necessary to write the configuration information of the [sshd] section into jail.local and restart the fail2ban service, otherwise, errors may occur when retrieving the blacklist.
- If the chosen ban method is multiport, only the ports configured, such as the default configuration's 22, will be banned during the ban process.
- If you need to modify the ban method, you must first determine whether the corresponding service is normally available.
    - RedHat/CentOS use the Firewall firewall.
    - Debian/Ubuntu use the UFW firewall.
- The log path needs to be modified based on the operating system.
    - For RedHat/CentOS, the log is /var/log/secure.
    - For Debian/Ubuntu, the log is /var/log/auth.log.
- Debian has abandoned rsyslog starting from version 12, and it needs to be installed manually before use.
