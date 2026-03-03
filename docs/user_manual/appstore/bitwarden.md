# Install Bitwarden Visually Using 1Panel

!!! note ""
    **Bitwarden** is an open‑source password manager that provides robust security and convenient password management. This repository uses an alternative server implementation of the Bitwarden client API, written in Rust, and is compatible with the official Bitwarden clients. It is ideal for self‑hosted deployments where running the official resource‑heavy service may not be optimal. After deploying the server, users can still use the official Bitwarden apps and browser extensions with the compatible API service.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)

## 2. Search for Bitwarden and Install

!!! note ""
    Enter **Bitwarden** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251020154143141](../../img/app/bitwarden.png)

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: bitwarden)
    - **Version**: Select the desired Bitwarden version from the dropdown
    - **Port**: Access port for the application (default: 40031)
    - **Port External Access**: When enabled, allows external network access to the application port

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251020154143141](../../img/app/bitwarden_install.png)

!!! note ""
    Wait for the installation to complete.

## 4. Configure Bitwarden SSL Access

!!! note ""
    Note: Bitwarden requires an SSL certificate for access. Direct access will result in a loading loop.

![image-20251021103933402](../../img/app/bitwarden_error.png)

!!! note ""
    Click **Websites** in the left menu, then select **Create Website**.

![image-20251021104405151](../../img/app/bitwarden_creat_proxy.png)

!!! note ""
    Click **Reverse Proxy**.

![image-20251021104522152](../../img/app/bitwarden_proxy.png)

!!! note ""
    Enter the domain and port for the reverse proxy, select **Bitwarden** as the application, then click **Confirm**.

![image-20251021111122113](../../img/app/bitwarden_proxy_info.png)

!!! note ""
    After the website is created successfully, click **Settings**.

![image-20251021110218133](../../img/app/bitwarden_con.png)

!!! note ""
    Select **HTTPS** on the left and enable HTTPS.

![image-20251021110452921](../../img/app/bitwarden_https.png)

!!! note ""
    Import your certificate or select an existing one, then click **Save** after configuration.

![image-20251021110637134](../../img/app/bitwarden_https_save.png)

## 5. Access the Bitwarden Service

!!! note ""
    Access the domain and port configured for the reverse proxy.

![image-20251021112440459](../../img/app/bitwarden_view.png)
