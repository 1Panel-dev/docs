!!! note ""
    **1Panel integrates two widely used Linux firewalls: Firewalld and UFW.**

    - Firewalld is used on RedHat/CentOS
    - UFW is used on Debian/Ubuntu

## 1 Installation

=== "RedHat / CentOS"
    !!! note ""
        **1. Update packages**

        ```bash
        sudo yum update
        ```

        **2. Install firewalld**
        
        ```bash
        sudo yum install firewalld
        ```

        **3. Start firewalld**
        
        ```bash
        sudo systemctl start firewalld
        ```
        
        **4. If you connect to your server remotely, you must explicitly allow SSH before enabling firewalld, or you will lose access.**

        ```bash
        sudo firewall-cmd --zone=public --add-port=22/tcp --permanent
        ```
        
        > If SSH uses a non‑standard port, replace 22 with your actual SSH port.
        
        **5. Allow the 1Panel port.**

        ```bash
        sudo firewall-cmd --zone=public --add-port=8090/tcp --permanent
        ```

        > Replace 8090 with your actual 1Panel port.

        **6. Reload firewall rules**

        ```bash
        sudo firewall-cmd --reload
        ```

        **7. Enable firewalld on boot**
        
        ```bash
        sudo systemctl enable firewalld
        ```

=== "Ubuntu / Debian"
    !!! note ""
        **1. Update packages**

        ```bash
        sudo apt update
        ```

        **2. Install UFW**
        
        ```bash
        sudo apt install ufw
        ```

        **3. If you connect to your server remotely, you must explicitly allow SSH before enabling UFW, or you will lose access.**

        ```bash
        sudo ufw allow 22/tcp
        ```
        
        > If SSH uses a non‑standard port, replace 22 with your actual SSH port.

        **4. Allow the 1Panel port.**

        ```bash
        sudo ufw allow 8090/tcp
        ```

        > Replace 8090 with your actual 1Panel port.

        **5. Enable UFW**
        
        ```bash
        sudo ufw enable
        ```

## 2 Firewall Status

!!! note ""
    **Click the firewall switch to turn it on or off.**
    
![img.png](../../img/hosts/firewall_switch.png)
{: .original}

!!! note ""
    **Click the Ping Disable button to enable or disable PING.**

    - Disabling PING prevents server performance degradation caused by frequent pings.

![img.png](../../img/hosts/firewall_ping.png)
{: .original}

## 3 Port Rules

!!! note ""
    **Click Create Port Rule to configure port access.**

    - Protocol: Default TCP; options: TCP, UDP, TCP/UDP
    - Port: Custom port (0–65535)
    - Source: Default All IPs; options: All IPs, Specified IP
    - Policy: Default Allow; options: Allow, Deny

!!! note ""
    **After allowing ports, you can view the current status in the firewall list.**

![img.png](../../img/hosts/firewall_port_list.png)
{: .original}

![img.png](../../img/hosts/firewall_port_create.png)
{: .original}

## 4 Port Forwarding

!!! note ""
    **Click Create Port Forwarding to set up forwarding rules.**

    - Protocol: Default TCP; options: TCP, UDP, TCP/UDP
    - Source Port: Packets to this port are forwarded to Target IP:Target Port (0–65535)
    - Target IP: For local forwarding, use 127.0.0.1; empty means local forwarding
    - Target Port: Port that receives forwarded traffic

![img.png](../../img/hosts/firewall_port_forward.png)
{: .original}

## 5 IP Rules

!!! note ""
    **Click Create IP Rule to set IP access policies.**

    - Specified IP
    - Policy: Default Allow; options: Allow, Block

![img.png](../../img/hosts/firewall_ip_list.png)
{: .original}

![img.png](../../img/hosts/firewall_ip_create.png)
{: .original}
