# Install OpenResty Visually Using 1Panel

!!! note ""
    **OpenResty** is a high-performance web application server based on Nginx. It integrates Nginx with the Lua programming language, providing powerful functionality and flexibility.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .original}

## 2. Search for OpenResty and Install

!!! note ""
    Enter **OpenResty** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251022205345484](../../img/app/openresty.png)
{: .original}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Default application name in the input field
    - **Version**: It is recommended to use the latest stable version
    - **HTTP Port**: Default 80 (can be adjusted if conflicting with existing services)
    - **HTTPS Port**: Default 443 (can be adjusted if conflicting with existing services)
    - **Website Directory**: The default website directory is placed under the 1Panel installation directory; please fill in an absolute path if you need to modify it
    
    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-20251022205428034](../../img/app/openresty_install.png)
{: .original}

## 4. Check Running Status

!!! note ""
    Go to the **Installed** page to view the running status of OpenResty. You can perform the following operations on the application:

    - **Rebuild**: Recreate the application  
    - **Restart**: Restart the running application
    - **Start / Stop**: Start or stop the application
    - **Uninstall**: Remove the application and its data
    - **View Parameters**: Check the application startup configuration
    - **View Logs**: View real-time application logs
    - **Enter Container Terminal**: Execute commands inside the container
    - **Backup / Restore**: Backup and restore application data

![image-20251022205720006](../../img/app/openresty_installed.png)
{: .original}

## 5. Use OpenResty

!!! note ""
    Go to the **Websites** menu on the left side of 1Panel to create new websites and use the OpenResty service.

![image-20251022205757786](../../img/app/openresty_view.png)
{: .original}
