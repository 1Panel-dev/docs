# Basic Settings

The website settings page offers a range of functionalities, including domain name configuration, directory management, default document setup, traffic limitation, reverse proxy, basic auth, HTTPS configuration, pseudo-static settings, redirection, and more.

## Domains

The `Domains` setting page allows users to manage the domain name and port configurations of their website.

## Directory

The `Directory` setting page allows users to view the website's root directory, set the runtime directory, and configure options such as the runtime user and group.

## Index files

The `Document` setting page defines files that will be used as an index.

## Traffic limits

Enables users to configure traffic limits, controlling the website's bandwidth and access traffic through the selection of different limit plans.

## Reverse proxy

The reverse proxy function allows the forwarding of website requests to backend servers, achieving load balancing, security control, and content distribution.

## Basic authentication

The `Basic authentication` feature enables users to set an access password for their website, enhancing the site's security by restricting unauthorized access.

## HTTPS

When configuring HTTPS for a website, users need to fill in or select the following information:

    - **HTTP Access Options**：Select the option for accessing the website via HTTP protocol, including: 
        - 1. Redirect to HTTPS; 
        - 2. Allow direct HTTP request;
        - 3. Block HTTP request.
    - **HSTS**：Enable HSTS to enhance website security.
    - **SSL Options**：Select an existing certificate or import a new one.
    - **Protocol Version**：Select the SSL protocol version.
    - **Encryption Algorithm**：Specify the SSL encryption algorithm.

## Pseudo-static

The pseudo-static function converts dynamic URLs into more user-friendly static URLs, improving the readability of the website and the SEO effect.

## Anti-leech

The anti-leech function verifies the source of requests to prevent unauthorized users from directly linking and downloading website resources, ensuring the security of website content.

## Redirect

The redirect function enables the automatic forwarding of requests accessing specific URLs to another URL, facilitating link management and traffic guidance.

## Other

In addition to the above settings, users can also perform operations such as changing the primary domain, switching groups, and updating remarks in `Other` settings.
