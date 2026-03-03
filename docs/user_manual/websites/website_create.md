!!! note ""
    Supports one‑click deployment of multiple website creation methods, including runtime environments (PHP, Java, Node.js, Go, Python), reverse proxies, and static websites, meeting the needs for rapid deployment of different types of websites.

## 1 One‑Click Deployment

!!! note ""
    You can easily deploy websites using applications from the App Store, such as WordPress and Halo.

    - **Group**: Select the group the website belongs to
    - **App Type**: Choose an installed app or install a new one
    - **App Parameters**: Fill in relevant parameters if installing a new app
    - **Primary Domain**: Enter the main domain and port to bind
    - **Other Domains**: Enter additional domains and ports to bind
    - **Listen on IPv6**: Allow the server to accept client requests via IPv6
    - **Alias**: Set the folder name for the website directory
    - **Enable HTTPS**: Turn on HTTPS and select an SSL certificate
    - **Remark**: Describe the purpose of the site

![img.png](../../img/websites/auto_create.png)
{: .browser-mockup}

## 2 Runtime Environment

!!! note ""
    You can create a website using an existing runtime environment.

    - **Group**: Select the group the website belongs to
    - **Type**: Choose the runtime type and an existing environment (supports PHP, Java, Node.js, Go, Python, .NET)
    - **Port**: Specify the port for the website service
    - **Primary Domain**: Enter the main domain and port to bind
    - **Other Domains**: Enter additional domains and ports to bind
    - **Listen on IPv6**: Allow the server to accept client requests via IPv6
    - **Alias**: Set an alias as the folder name for the website directory
    - **Create FTP**: Create an FTP account for the site with the directory pointing to the site folder
    - **Create Database**: Create a database for the site at the same time
    - **Enable HTTPS**: Turn on HTTPS and select an SSL certificate
    - **Remark**: Describe the function of the site

![img.png](../../img/websites/website_runtime_create.png)
{: .browser-mockup}

## 3 Reverse Proxy

!!! note ""
    Supports creating reverse proxy websites to forward requests to other services.

    - **Group**: Select the group the website belongs to
    - **Primary Domain**: Enter the main domain and port to bind
    - **Other Domains**: Enter additional domains and ports to bind
    - **Listen on IPv6**: Allow the server to accept client requests via IPv6
    - **Alias**: Set the folder name for the website directory
    - **Proxy Address**: Enter the address of an existing service or select from installed apps
    - **Enable HTTPS**: Turn on HTTPS and select an SSL certificate
    - **Remark**: Describe the function or purpose of the site

![img.png](../../img/websites/proxy_create.png)
{: .browser-mockup}

## 4 Static Website

!!! note ""
    Supports quick creation of static websites with convenient deployment and management, allowing you to easily publish and maintain static content.
    
    - **Group**: Select the group the website belongs to
    - **Primary Domain**: Enter the main domain and port to bind
    - **Other Domains**: Enter additional domains and ports to bind
    - **Listen on IPv6**: Allow the server to accept client requests via IPv6
    - **Alias**: Set an alias as the folder name for the website directory
    - **Create FTP**: Create an FTP account for the site with the directory pointing to the site folder
    - **Enable HTTPS**: Turn on HTTPS and select an SSL certificate
    - **Remark**: Briefly describe the function or purpose of the site

![img.png](../../img/websites/static_create.png)
{: .browser-mockup}

## 5 Sub‑Website

!!! note ""
    Create a sub‑website for an existing PHP or static website. The sub‑website can use a subdirectory of the parent site as its root directory.
    
    - **Group**: Select the group the website belongs to
    - **Parent Website**: Select the parent website of this sub‑site
    - **Runtime Directory**: Choose a subdirectory under the parent site’s runtime directory
    - **Primary Domain**: Enter the main domain and port to bind
    - **Other Domains**: Enter additional domains and ports to bind
    - **Listen on IPv6**: Allow the server to accept client requests via IPv6
    - **Alias**: Set an alias as the folder name for the website directory
    - **Enable HTTPS**: Turn on HTTPS and select an SSL certificate
    - **Remark**: Briefly describe the function or purpose of the site

![img.png](../../img/websites/subsite_create.png)
{: .browser-mockup}
