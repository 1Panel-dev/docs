# Install OpenList Visually Using 1Panel

!!! note ""
    **OpenList** is a file listing program that supports multiple storage backends, web browsing, and WebDAV. It is powered by gin and Solidjs.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-appstores](../../img/app/appstores.png)
{: .original}

## 2. Search for OpenList and Install

!!! note ""
    Enter **OpenList** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-openlist](../../img/app/openlist.png)
{: .original}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: openlist)
    - **Version**: Select the desired OpenList version from the dropdown
    - **WebUI Port**: Access port for the application (default: 5244)
    - **S3 Port**: Access port for the S3 service (default: 5246)
    - **Pre-installed Tools**: Optional `Thumbnails (ffmpeg)` / `Offline Download (aria2)` / `All (ffmpeg & aria2)`
    - **Timezone**: Defaults to `Asia/Shanghai`
    - **Port External Access**: When enabled, allows external network access to the application ports

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-openlist_install](../../img/app/openlist_install.png)
{: .original}

!!! note ""
    Wait for the installation to complete.

## 4. Default Account & Password

!!! note ""
    Click **Containers** in the left menu, find the OpenList container, and click **Terminal**.

![image-openlist_set_pwd](../../img/app/openlist_set_pwd.png)
{: .original}

!!! note ""
    Connect to the terminal and generate a password using one of the two methods:

    - **Generate random password**: `./openlist admin random`
    - **Set password manually**: `./openlist admin set NEW_PASSWORD`

![image-openlist_passwd](../../img/app/openlist_passwd.png)
{: .original}

## 5. Access the OpenList Service

!!! note ""
    After installation, confirm the default access address in 1Panel. Skip this step if already configured.

![image-setting-ip](../../img/app/setting_ip.png)
{: .original}

!!! note ""
    Return to the App Store and click **Jump** to access the OpenList service.

![image-openlist_jump](../../img/app/openlist_jump.png)
{: .original}

!!! note ""
    Enter the generated password to log in.

![image-openlist_view](../../img/app/openlist_view.png)
{: .original}
