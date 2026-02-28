# Install Gitea Visually Using 1Panel

!!! note ""
    **Gitea** is a next-generation code hosting platform with core Git-based code hosting capabilities and extended DevSecOps features. It provides developers with an experience similar to GitHub and supports private self-hosted deployment.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .original}

## 2. Search for Gitea and Install

!!! note ""
    Enter **Gitea** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251017152422217](../../img/app/gitea.png)
{: .original}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: gitea)
    - **Version**: Select the desired Gitea version from the dropdown
    - **Database Service**: Select the database service for data storage, such as PostgreSQL
    - **Database Name**: Name of the database created for the application
    - **Database User**: Username for database connection
    - **Database Password**: Password for the database user
    - **HTTP Port**: Web access port (default: 3000)
    - **SSH Port**: Access port for Git over SSH (default: 222)
    - **Port External Access**: When enabled, allows external network access to the application ports

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251017152504426](../../img/app/gitea_install.png)
{: .original}

!!! note ""
    Wait for the installation to complete.

## 4. Access the Gitea Service

!!! note ""
    Configure the default access address. Skip this step if already configured.

![image-20251016172322315](../../img/app/setting_ip.png)
{: .original}

!!! note ""
    Return to the App Store and click **Jump** to access the Gitea service.

![image-20251017152732221](../../img/app/jump_gitea.png)
{: .original}

!!! note ""
    Complete the initial configuration and install the service.

![image-20251017152844763](../../img/app/gitea_info.png)
{: .original}

!!! note ""
    You can use Gitea after installation is finished.

![image-20251017153119824](../../img/app/gitea_view.png)
{: .original}
