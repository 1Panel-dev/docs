# Create a Website

Supports various website creation methods, including deployed applications, runtime environments (PHP, Java, Node.js, Go, Python), reverse proxy, and static websites, to meet the fast construction needs of different types of websites.

## General Settings

!!! note "Parameters"
    - **Group**: Select the group to which the website belongs;
    - **Primary domain**: Enter the primary domain name and its port to be bound;
    - **Other domains**: Enter other domain names and their ports to be bound;
    - **Listen IPv6**: Enable the server to receive client requests through IPv6 addresses;
    - **Alias**: Set the folder name for the website directory;
    - **Description**: Write a description of the purpose of the site;

## Website backed with Application

You can easily deploy a website using applications provided in the App Store, such as WordPress.

!!! note "Parameters"
    - **Application Type**: Select an installed application or a new application to install;
    - **Application Parameters**: If you choose to install a new application, please fill in the relevant parameters;

## Website backed with Runtime

You can create a website using the added runtime environment.

!!! note "Parameters"
    - **Type**: Select the type of runtime environment (currently supports PHP, Java, Node.js, Go, and Python);
    - **Runtime**: Choose a created runtime environment;
    - **FTP**: Create an FTP account corresponding to the site, with the FTP directory pointing to the site's directory;

## Reverse proxy

Create a reverse proxy website to forward requests to other services on this server or other servers.

!!! note "Parameters"
    - **Proxy Address**: Enter the address of the existing service;

## Static website

Create a static website, providing streamlined deployment and management capabilities, simplifying the process for users to publish and maintain static content.

!!! note "Parameters"
    - **FTP**: Create an FTP account corresponding to the site, with the FTP directory pointing to the site's directory;
