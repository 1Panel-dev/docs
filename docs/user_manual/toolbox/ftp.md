
# FTP

## Introduction

1Panel uses [Pure-FTPd](https://www.pureftpd.org/project/pure-ftpd/) as the FTP server. Pure-FTPd is a free (BSD), secure, production-quality and standard-conformant FTP server. It doesn’t provide useless bells and whistles, but focuses on efficiency and ease of use. It provides simple answers to common needs, plus unique useful features for personal users as well as hosting providers.

## Installing Pure-FTPd

=== "RedHat / CentOS"
    1. Install the EPEL repository
    ```shell
    yum install -y epel-release
    ```
    2. Install Pure-FTPd
    ```shell
    yum -y install pure-ftpd
    ```
    3. Configure Pure-FTPd
    ```shell
    # The default configuration is located at /etc/pure-ftpd/pure-ftpd.conf. Modify the following parameters in the configuration file:
    ## Specify the path for the PureDB user database file
    PureDB /etc/pure-ftpd/pureftpd.pdb
    ## Enable logging
    VerboseLog yes
    ## Disable anonymous login
    NoAnonymous yes
    ## Enable and adjust the passive port range as needed
    PassivePortRange 39000 40000
    ```
    4. Start the Pure-FTPd service
    ```shell
    systemctl start pure-ftpd.service
    ```
    5. Enable Pure-FTPd to start at boot
    ```shell
    systemctl enable pure-ftpd.service
    ```
    6. Check the status of the Pure-FTPd service
    ```shell
    systemctl status pure-ftpd.service
    ```

=== "Ubuntu / Debian"
    1. Install Pure-FTPd
    ```shell
    sudo apt-get install pure-ftpd
    ```
    2. Configure Pure-FTPd
    ```shell
    ## Specify the path for the PureDB user database file
    echo '/etc/pure-ftpd/pureftpd.pdb' > /etc/pure-ftpd/conf/PureDB
    ## Enable logging
    echo 'yes' > /etc/pure-ftpd/conf/VerboseLog
    ## Disable anonymous login
    echo 'yes' > /etc/pure-ftpd/conf/NoAnonymous
    ## Enable and adjust the passive port range as needed
    echo '39000 40000' > /etc/pure-ftpd/conf/PassivePortRange
    ```
    3. Create a symbolic link for the database
    ```shell
    ln -s /etc/pure-ftpd/conf/PureDB /etc/pure-ftpd/auth/50puredb
    ```
    4. Start the Pure-FTPd service
    ```shell
    systemctl start pure-ftpd.service
    ```
    5. Enable Pure-FTPd to start at boot
    ```shell
    systemctl enable pure-ftpd.service
    ```
    6. Check the status of the Pure-FTPd service
    ```shell
    systemctl status pure-ftpd.service
    ```
