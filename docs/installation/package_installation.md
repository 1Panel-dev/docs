## 1. Features

!!! note "Fully Standalone Operation"
    - The offline version does not connect to the internet or send any network requests.
    - Integrates all features of the community edition and runs independently in offline environments.
    - Ideal for deployment in enterprise intranets, offline computer rooms, and classified environments.

!!! note "App Store Support"
    - Common application images are pre-included in the offline package and automatically imported after installation:
        - **OpenResty Version**: `1.27.1.2-2-3-focal`
        - **MySQL Versions**:
            - **x86_64 Package**: `8.4.6`, `8.0.43`, `5.7.44`, `5.6.51`
            - **arm64 Package**: `8.4.6`, `8.0.43`
    - Beyond built-in images, users can install other applications by importing external images:
        - Other applications require manual image import before use (see [Import Application Images](#72-import-images) for tutorial).
    - Once imported successfully, images appear in the 1Panel App Store for installation with high flexibility.

!!! note "Mainstream Xinchuang Support"
    - Supports mainstream Xinchuang environments (Hygon, Kunpeng, Kylin, Euler), ensuring stable operation across diverse domestic hardware/software ecosystems.

!!! note "Automatic Docker Installation"
    - If Docker is not detected during installation, the script automatically installs Docker.

## 2. Environment Requirements

!!! note ""
    - **Operating System**: Supports mainstream Linux distributions (Debian/RedHat-based, including domestic OSes)
    - **Server Architecture**: `x86_64` and `arm64`
    - **Memory**: Recommended available memory ≥ **1GB**
    - **Browser**: Use modern browsers such as **Chrome, Firefox**

## 3. Download Offline Package

!!! note ""
    ⚠️ **Important Warning: Do NOT purchase or download so-called "1Panel offline packages" from unofficial platforms like Xianyu**  
    🚫 These are **unauthorized pirated sources** — we cannot guarantee their security. They may be tampered with, contain trojans/viruses, and pose risks of server intrusion or data leakage.

    ✅ **Official Purchase Channel (Secure & Trusted)**

    - **Pricing**: Offline version ¥99 per download (current promotional price: ¥29 per download)
    - **Purchase Link**: https://jsj.top/f/sbCqY6

    > After successful payment, we will immediately send the exclusive download link for the 1Panel V2 offline package to the email you provided. Please check your inbox promptly. For issues, contact: `wanghe@fit2cloud.com`

    > Invoices are not currently available for the 1Panel offline version.

## 4. Installation and Deployment

### 4.1 Extract Offline Package

!!! note ""
    Download the latest 1Panel offline package, upload it to the `/tmp` directory of your server, and execute the following commands as the **root user** to prepare for installation:

    ```bash
    cd /tmp
    # Extract the offline package (replace the example filename with your actual filename)
    tar zxvf 1panel-v2.0.11-offline-linux-amd64.tar.gz
    ```

### 4.2 Run Installation Script

!!! note ""
    ```bash
    # Enter the extracted directory (replace with your actual directory name)
    cd 1panel-v2.0.11-offline-linux-amd64
    
    # Execute the installation script
    /bin/bash install.sh
    ```

## 5. Version Upgrade

### 5.1 Extract Offline Package

!!! note ""
    Download the latest 1Panel offline package, upload it to the `/tmp` directory of your server, and execute the following commands as the **root user** to prepare for upgrade:

    ```bash
    cd /tmp
    # Extract the offline package (replace the example filename with your actual filename)
    tar zxvf 1panel-v2.0.12-offline-linux-amd64.tar.gz
    ```

### 5.2 Run Upgrade Script

!!! note ""
    ```bash
    # Enter the extracted directory (replace with your actual directory name)
    cd 1panel-v2.0.12-offline-linux-amd64

    # Execute the upgrade script
    /bin/bash upgrade.sh
    ```

## 6. Access the Panel

!!! note ""
    After successful installation, the console displays panel access information. Access via browser:

    ```
    http://<Target Server IP>:<Target Port>/<Security Entrance>
    ```

    - **For cloud servers, ensure the target port is open in the security group**
    - **Run `1pctl user-info` to view the security entrance**

!!! note ""
    After installation, use the [1pctl command-line tool](cli.md) for daily maintenance.

## 7. App Store

### 7.1 Obtain Images

=== "Application Images"
    !!! note ""
        After clicking an application's **Install** button, check the `image:` field in **Advanced Settings** → **Edit Compose File** — the value after this field is the target image name.

=== "Java Runtime Environment"
    !!! note ""
        - bitnamilegacy/java:1.8
        - bitnamilegacy/java:11
        - bitnamilegacy/java:17
        - bitnamilegacy/java:21
        - bitnamilegacy/java:22

=== "Node.js Runtime Environment"
    !!! note ""
        - node:12.22.12
        - node:14.21.3
        - node:16.20.2
        - 1panel/node:18.20.8
        - 1panel/node:20.19.5
        - 1panel/node:21.7.3
        - 1panel/node:22.21.0
        - 1panel/node:24.10.0

=== "Go Runtime Environment"
    !!! note ""
        - golang:1.21
        - golang:1.22
        - golang:1.23
        - golang:1.24
        - golang:1.25

=== "Python Runtime Environment"
    !!! note ""
        - python:3.10.19
        - python:3.11.14
        - python:3.12.12
        - python:3.13.9
        - python:3.14.0

=== ".NET Runtime Environment"
    !!! note ""
        - mcr.microsoft.com/dotnet/aspnet:6.0
        - mcr.microsoft.com/dotnet/aspnet:7.0
        - mcr.microsoft.com/dotnet/aspnet:8.0
        - mcr.microsoft.com/dotnet/aspnet:9.0
        - mcr.microsoft.com/dotnet/aspnet:10.0

### 7.2 Import Images

!!! note ""
    To use other applications (e.g., WordPress) or runtime environments, manually import images with these steps:

    1. **Pull and export images on an internet-connected machine**:
        ```bash
        docker pull wordpress:6.8.2
        docker save -o /tmp/wordpress_6.8.2.tar wordpress:6.8.2
        ```

    2. **Upload the image file** to the `/tmp` directory of the 1Panel server:
        ```bash
        scp /tmp/wordpress_6.8.2.tar root@<1Panel Offline Server IP>:/tmp/
        ```

    3. **Import the image** on the 1Panel server:
        ```bash
        docker load -i /tmp/wordpress_6.8.2.tar
        ```

    After completing these steps, you can install the WordPress application from the App Store.
    For runtime environment images, the corresponding version becomes available for installation after import.

### 7.3 Update Applications / Runtime Environments

!!! note ""
    The offline App Store update feature requires **v2.0.13-offline or higher**. If your version is lower, upgrade first.

!!! note ""
    To sync the latest App Store content in an offline environment:

    1. **Download the latest App Store code on an internet-connected machine**:
        ```bash
        cd /tmp
        git clone https://github.com/1Panel-dev/appstore
        ```

    2. **Create an App Store archive**:
        ```bash
        cd appstore
        tar -zcf appstore.tar.gz apps data.yaml
        ```

    3. **Upload the archive to the offline server**:
        ```bash
        scp appstore.tar.gz root@<1Panel Offline Server IP>:~
        ```

    4. **Overwrite existing App Store files on the offline server (default install path: `/opt/1panel`)**:
        ```bash
        cd /opt/1panel/resource/offline
        mv appstore.tar.gz appstore.tar.gz.bak
        mv ~/appstore.tar.gz ./
        ```

    5. **Go to the App Store page and click "Sync Custom Applications" — the system automatically extracts and loads the latest App Store content.**

    These steps update the offline server with the latest App Store content.

## 8. PHP Offline Version

!!! note "Prepare Environment"
    - 1Panel V2 offline server
    - 1Panel V2 internet-connected server

    > Core operation: Import precompiled PHP images from the internet-connected server to the offline server.

### 8.1 Internet-Connected 1Panel

!!! note ""
    Create a PHP runtime environment in the internet-connected 1Panel and install required extensions (**record the image name and port**):

![offline_php_01](../../img/offline/offline_php_01.png)

!!! note ""
    Package the PHP image using the **image name** from the previous step — run these commands in `/opt/1panel/runtime/php/<PHP Environment Name>`:
    ```bash
    docker save -o php-8.4.6.tar 1panel-php-fpm:8.4.6
    ```

!!! note ""
    Compress the runtime environment directory — run in `/opt/1panel/runtime/php/`:
    ```bash
    tar -czvf php846.tar.gz <PHP Environment Name>
    ```

### 8.2 Offline 1Panel

!!! note ""
    Copy the compressed file to `/opt` (or another directory) and extract it:
    ```bash
    tar -xzvf php846.tar.gz
    ```

!!! note ""
    Enter the extracted directory, load the image, and start the PHP runtime environment:
    ```bash
    docker load -i php-8.4.6.tar
    docker compose up
    ```

    View two parameters with `cat .env`:
    - PANEL_APP_PORT_HTTP (PHP runtime environment port)
    - PANEL_WEBSITE_DIR (website directory)

    > Note: PANEL_WEBSITE_DIR must match the website directory used during OpenResty installation. Modify the .env file if they differ.

!!! note ""
    Create a local PHP runtime environment:

![offline_php_02](../../img/offline/offline_php_02.png)

!!! note ""
    Create a PHP website:
    > Note: Use the port of your running PHP runtime environment for the port field.

![offline_php_03](../../img/offline/offline_php_03.png)

## 9. Application Installation Notes

!!! note ""
    There are differences between installing applications in the offline version vs. via "Local Applications", mainly:

### 9.1 Comparison

| Method | Application Source | Includes All Applications | Automatically Integrates Feature Menus |
|--------|--------------------|---------------------------|----------------------------------------|
| Offline Version Installation | Pre-included in offline package | ✅ Yes | ✅ Yes (e.g., websites, databases) |
| Local Application Installation | Manually uploaded by user | ❌ No | ❌ No |

### 9.2 Recommended Use Cases

!!! note ""
    - **Offline Version Installation**: Ideal for fast deployment in network-free environments with complete features and optimal experience.  
        - Example: Applications like `OpenResty` and `MySQL` automatically integrate with **Website Management** and **Database Management** after installation, allowing direct creation of websites and databases.  
    - **Local Application Method**: Suitable for testing custom application packages or installing applications not in the official App Store.
