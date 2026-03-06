# Install RustDesk Visually Using 1Panel

!!! note ""
    **RustDesk** is an open-source remote support and remote desktop tool designed to provide users with convenient remote assistance and remote access capabilities.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .browser-mockup}

## 2. Search for RustDesk and Install

!!! note ""
    Enter **RustDesk** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251021135819982](../../img/app/rustdesk.png)
{: .browser-mockup}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: rustdesk)
    - **Version**: Select the desired RustDesk version from the dropdown
    - **NAT Type Test Port**: Defaults to 21115
    - **hbbs Port (for relay server)**: Defaults to 21116
    - **hbbr Port (client-client relay server port)**: Defaults to 21117
    - **Web Client Port 1**: Defaults to 21118
    - **Web Client Port 2**: Defaults to 21119
    - **IP Address or Domain (Required)**: Enter the public IP address or domain name of the server
    - **Port External Access**: When enabled, allows external network access to the application ports

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251021140057677](../../img/app/rustdesk_install.png)
{: .browser-mockup}

!!! note ""
    Wait for the installation to complete.

## 4. Configure and Use RustDesk

!!! note ""
    Click **Parameters** to get the configuration information.

![image-20251021142500835](../../img/app/rustdesk_get_info.png)
{: .browser-mockup}

!!! note ""
    Enter the installation directory.

![image-20251021142617880](../../img/app/rustdesk_install_view.png)
{: .browser-mockup}

!!! note ""
    Locate the corresponding pub file and retrieve the key.

![image-20251021142841367](../../img/app/rustdesk_key.png)
{: .browser-mockup}

!!! note ""
    Download the client from https://github.com/rustdesk/rustdesk/releases. After downloading, open the client, go to Settings, and select Relay Server.

![image-20251021141554097](../../img/app/rustdesk_info.png)
{: .browser-mockup}

!!! note ""
    Fill in the corresponding information.

![image-20251021142939475](../../img/app/rustdesk_creat.png)
{: .browser-mockup}

!!! note ""
    On the client of another host, fill in the same information, then enter the connection details to establish a remote connection.

![image-20251021143340226](../../img/app/rustdesk_view.png)
{: .browser-mockup}
