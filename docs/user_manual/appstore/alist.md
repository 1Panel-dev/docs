# Install AList Visually Using 1Panel

!!! note ""
    **AList** is a file listing program that supports multiple storage providers, web browsing, and WebDAV. It is powered by gin and Solidjs.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .original}

## 2. Search for AList and Install

!!! note ""
    Enter **AList** in the search box in the upper right corner, click the application card to go to the details page, and select **Install**.

![image-20251017093725067](../../img/app/alist.png)
{: .original}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: alist)
    - **Version**: Select the desired AList version from the dropdown
    - **WebUI Port**: Port for the web management interface (default: 5244)
    - **S3 Port**: Port for the S3 service (default: 5246)
    - **Port External Access**: When enabled, allows external network access to the application ports

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251017095132628](../../img/app/alist_install.png)
{: .original}

!!! note ""
    Wait for the installation to complete.

## 4. Configure Access to the AList Service

!!! note ""
    After installation, confirm the default access address in 1Panel. Skip this step if already configured.

![image-20251016172322315](../../img/app/setting_ip.png)
{: .original}

!!! note ""
    Click **Containers** in the left menu, find the AList container, and click **Terminal**.

![image-20251017101043569](../../img/app/alist_set_pwd.png)
{: .original}

!!! note ""
    Connect to the terminal and generate a password. Two methods are available:

    - **Generate random password**: `./alist admin random`
    - **Set password manually**: `./alist admin set NEW_PASSWORD`

![image-20251017101434307](../../img/app/alist_passwd.png)
{: .original}

!!! note ""
    Return to the App Store and click **Jump** to access the AList service.

![image-20251017101728523](../../img/app/alist_jump.png)
{: .original}

!!! note ""
    Enter the generated password to log in.

![image-20251017101943414](../../img/app/alist_view.png)
{: .original}
