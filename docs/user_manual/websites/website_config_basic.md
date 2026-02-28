!!! note ""
    The website settings page includes a wide range of functions, including domain settings, website directory, default documents, traffic limits, reverse proxy, load balancing, password access, HTTPS configuration, real IP, pseudo-static, anti-leech, redirection, associated databases, and other settings.

## 1 Domain Settings

!!! note ""
    The domain settings page allows you to manage the domain names and port configurations for the website.

![img.png](../../img/websites/config_basic_domain.png)
{: .browser-mockup}

## 2 Website Directory

!!! note ""
    The website directory page supports viewing the website root directory, setting the runtime directory, and configuring the runtime user and user group.

![img.png](../../img/websites/config_basic_folder.png)
{: .browser-mockup}

## 3 Default Document

!!! note ""
    Configure the default document to automatically load a specified file when users access the website root directory.

![img_1.png](../../img/websites/basic_config_default.png)
{: .browser-mockup}

## 4 Traffic Limit

!!! note ""
    Allows you to configure traffic limits and control website bandwidth and access traffic by selecting different restriction policies.

![img.png](../../img/websites/basic_config_limit.png)
{: .browser-mockup}

## 5 Reverse Proxy

!!! note ""
    The reverse proxy function forwards website requests to backend servers for load balancing, security control, and content delivery.

![img.png](../../img/websites/basic_config_proxy.png)
{: .browser-mockup}

!!! note ""
    You can also enable and configure reverse proxy cache rules or clear the current cache on this page.

![img.png](../../img/websites/basic_config_proxy_cache.png)
{: .browser-mockup}

## 6 Load Balancing

!!! note ""
    Create load balancing rules to forward website requests to multiple backend services. This page only creates the rules; to use them, set the reverse proxy target to `http://<load-balancer-name>`.

![img.png](../../img/websites/basic_config_upstream.png)
{: .browser-mockup}

## 7 Password Access

!!! note ""
    The password access function lets you set an access password for the website to enhance security and restrict unauthorized access. Supports global or path‑specific configuration.

![img.png](../../img/websites/basic_config_password.png)
{: .browser-mockup}

## 8 HTTPS

!!! note ""
    When configuring HTTPS for the website, you need to fill in or select:

    - **HTTP Option**: Access mode
        - Auto redirect HTTP to HTTPS
        - Allow direct HTTP access
        - Deny HTTP access
    - **HSTS**: Enable HSTS for improved security
    - **HTTP3**: Enable HTTP3 for faster connections (not all browsers support it)
    - **SSL Option**: Select an existing certificate or manually import one
        - **Acme Account (existing certificate)**: Select an existing ACME account
        - **Certificate (existing certificate)**: Select an existing certificate
        - **Import Method (manual import)**: Paste content or select a file
        - **Private Key (manual import)**: Private key content or path
        - **Certificate (manual import)**: Certificate content or path
    - **Supported Protocol Versions**: Select SSL protocol versions
    - **Cipher Suites**: Specify SSL encryption algorithms

    These configurations effectively improve website security and performance.
    
![img.png](../../img/websites/basic_config_https.png)
{: .browser-mockup}

## 9 Real IP

!!! note ""
    Configure how the client IP is obtained and trusted IP sources. OpenResty parses IP information from HTTP headers to accurately identify and log visitors’ real IP addresses.

![img.png](../../img/websites/basic_config_real_ip.png)
{: .browser-mockup}

## 10 Pseudo-Static

!!! note ""
    The pseudo‑static function converts dynamic URLs into user‑friendly static URLs to improve readability and SEO.

![img.png](../../img/websites/basic_config_static.png)
{: .browser-mockup}

## 11 Anti-Leech

!!! note ""
    The anti‑leech function verifies request origins to prevent unauthorized direct linking and downloading of website resources, protecting content security.

![img.png](../../img/websites/basic_config_protection.png)
{: .browser-mockup}

## 12 Redirection

!!! note ""
    The redirection function automatically forwards requests for a specific URL to another URL for link management and traffic guidance.

![img.png](../../img/websites/basic_config_redirect.png)
{: .browser-mockup}

## 13 PHP

!!! note ""
    Static websites can switch to PHP type by selecting a PHP runtime environment. PHP websites can switch between different PHP environments.

![img.png](../../img/websites/basic_config_php.png)
{: .browser-mockup}

## 14 Resource

!!! note ""
    Associate the current website with a database. Backing up the website will also back up the associated database. Switching databases may break previous backups.

![img.png](../../img/websites/basic_config_resource.png)
{: .browser-mockup}

## 15 Other

!!! note ""
    Supports changing the primary domain, switching groups, and updating remarks.

![img.png](../../img/websites/basic_config_other.png)
{: .browser-mockup}
