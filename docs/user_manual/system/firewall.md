
# Firewall

1Panel integrates two widely used Linux firewall software: Firewalld and UFW.

- Firewalld is used by RedHat/CentOS.
- UFW is used by Debian/Ubuntu.

## Installation

=== "RedHat / CentOS"
    1. Update the repository
    ```shell
    sudo yum update
    ```
    2. Install firewalld
    ```shell
    sudo yum install firewalld
    ```
    3. Start the firewalld service
    ```shell
    sudo systemctl start firewalld
    ```
    4. Before enabling the firewalld firewall, you must explicitly allow incoming SSH connections if you are connecting to your server remotely. Otherwise, you will never be able to connect to the machine.
    ```shell
    sudo firewall-cmd --zone=public --add-port=22/tcp --permanent
    ```

        !!! tips "Tips"
            If SSH is running on a non-standard port, you need to replace the 22 port in the above command with the corresponding SSH port.
    
    5. Open the 1Panel system port.
    ```shell
    sudo firewall-cmd --zone=public --add-port=8090/tcp --permanent
    ```
   
        !!! tips "Tips"
            The 8090 port in the above command needs to be replaced with the custom port set during the installation of the 1Panel.

    6. Reload the firewall rules to apply the changes
    ```shell
    sudo firewall-cmd --reload
    ```
    7. Enable firewalld to start at boot
    ```shell
    sudo systemctl enable firewalld
    ```

=== "Ubuntu / Debian"
    1. Update the repository
    ```shell
    sudo apt update
    ```
    2. Install UFW
    ```shell
    sudo apt install ufw
    ```
    3. Before enabling the UFW firewall, you must explicitly allow incoming SSH connections if you are connecting to your server remotely. Otherwise, you will never be able to connect to the machine.
    ```shell
    sudo ufw allow 22/tcp
    ```

        !!! tips "Tips"
            If SSH is running on a non-standard port, you need to replace the 22 port in the above command with the corresponding SSH port.

    4. Open the 1Panel system port.
    ```shell
    sudo ufw allow 8090/tcp
    ```
   
        !!! tips "Tips"
            The 8090 port in the above command needs to be replaced with the custom port set during the installation of the 1Panel.

    5. Start UFW
    ```shell
    sudo ufw enable
    ```

## Port rule

By clicking the `Create Rule` button, you can set up port rules.

- Protocol: The default is TCP protocol, with options including TCP, UDP, and TCP/UDP protocols. Choose based on your actual needs.
- Port: Enter the port you want to set the rule for, customizable, with a port range of 0-65535.
- Source: The default is all IPs, with options including all IPs and specific IPs.
- Policy: The default is allow, with options including allow and deny.

!!! tips "Tips"
    **After successfully opening a port, you can view the firewall list to check the current port's operation status.**

## Port-forward rule

Click the `Create Port-Forward rule` button to set up a port forwarding rule.

- Protocol: Default is TCP protocol, with options including TCP, UDP, and TCP/UDP protocols. Choose based on your actual needs.
- Source Port: The packet sent to the source port will be forwarded to `Target IP:Target Port`, with a port range of 0-65535.
- Destination IP: If it is local port forwarding, the target IP is: 127.0.0.1; if the target IP is not filled in, it defaults to local port forwarding.
- Destination Port: The target port that receives the forwarded packet.

## IP rule

By clicking the `Create IP Rule` button, you can set up IP rules.
