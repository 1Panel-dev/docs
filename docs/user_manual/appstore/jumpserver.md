# Install JumpServer Visually Using 1Panel

!!! note ""
    **JumpServer** is a widely popular open‑source bastion host and a professional operation and maintenance security audit system that complies with 4A specifications. JumpServer bastion host helps enterprises securely manage and log in to various types of assets.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .browser-mockup}

## 2. Search for JumpServer and Install

!!! note ""
    Enter **JumpServer** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251021154330947](../../img/app/jumpserver.png)
{: .browser-mockup}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: jumpserver)
    - **Version**: Select the desired JumpServer version from the dropdown
    - **Secret Key**: Set the signature key for data encryption
    - **Bootstrap Token**: Set the token for authentication between JumpServer internal components
    - **Debug Mode**: Enable or disable debug mode (default: off)
    - **Log Level**: Select the application log output level (default: ERROR)
    - **Database Service**: Select the database service for data storage, such as PostgreSQL
    - **Database**: Name of the database created for the application
    - **Database User**: Username for database connection
    - **Database Password**: Password for the database user
    - **Redis Service**: Select the Redis service for caching
    - **Redis Password**: Password for the Redis service
    - **Use Built-in Nginx**: Choose whether to use the built-in Nginx of JumpServer
    - **HTTP Port**: Web access port (default: 8080)
    - **SSH Port**: Access port for SSH service (default: 2222)
    - **Domain**: Set the access domain for JumpServer

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251021160652472](../../img/app/jumpserver_install.png)
{: .browser-mockup}

!!! note ""
    Wait for the installation to complete.

## 4. Access the JumpServer Service

!!! note ""
    After installation, confirm the default access address in 1Panel. Skip this step if already configured.

![image-20251016172322315](../../img/app/setting_ip.png)
{: .browser-mockup}

!!! note ""
    Return to the App Store and click **Jump** to access the JumpServer service.

![image-20251021162640135](../../img/app/jumpserver_jump.png)
{: .browser-mockup}

!!! note ""
    Log in with the default credentials: Username `admin`, Password `ChangeMe`.

![image-20251021162912802](../../img/app/jumpserver_view.png)
{: .browser-mockup}
