
# Request a Certificate

To apply for a free certificate, domain ownership verification is required. The simplified application process is as follows:

1. Fill in domain information of the SSL certificate
2. Submit a certificate application request through ACME
3. Verify domain ownership
    1. **Automatic Verification with DNS Account**: Automatically add DNS records for verification by calling the DNS service provider's interface
    2. **Manual Resolution Verification**: Manually add DNS records for verification
    3. **Verify with HTTP mode**: Verify through HTTP request like `http://domainname.com/.well-known/acme-challenge/z_ih8hZD2lxSZORxB-SzqbVfMkZdqvXenlwbURdibGA`

## Prerequisites

- An available DNS domain name
- [A supported DNS provider](#supported-dns-providers) for the DNS account verification method
- The OpenResty application must be installed prior to using the HTTP verification method
- The domain name of the SSL certificate must resolve to the current 1Panel server when using the HTTP verification method

## General Parameters

!!! note "Parameters"
    - **Primary domain**: Enter the primary domain name of the SSL certificate;
    - **Other domains**: Enter other domain names of the SSL certificate;
    - **Remark**: Write a description of the SSL certificate;
    - **Push the certificate to the local directory**: If the certificate needs to be used in other applications, you can use this option to automatically copy the applied and updated certificate to a specified directory;
    - **Execute the script after certificate request**: This feature can be used when additional operations are required after certificate application or update, such as copying certificates to other servers or updating certificates used by CDNs;
    - **Disable CNAME**: Check here if the domain name has a CNAME record and the request fails;
    - **Skip DNS check**: Check here only if you encounter a timeout issue during certification request;
    - **DNS server**: Use a custom DNS server to verify domain names.

!!! tip "Tips"
    For wildcard domain names, `*.domainname.com` can be used.

## Automatic Verification with DNS Account

Upon submitting the basic information and selecting the DNS provider account, 1Panel will automatically complete the domain verification process by calling the DNS provider's API. 

When `Automatic Renewal` is checked, 1Panel will automatically renew the certificate before it expires and deploy the renewed certificate to the website using it.

!!! tip "Tips"
    You can find supported DNS providers [here](./certificate_dns.md).

## Manual Resolution Verification

After filling in the certificate information and clicking confirm, you need to manually click the `Apply` button to generate DNS resolution records.

You must manually add the corresponding resolution records in the DNS provider's console, and after completing the addition, click the `Confirm` button to complete the certificate application process.

## Verify with HTTP mode

Upon submitting the certificate information and confirming, 1Panel automatically generates and adds the verification file to OpenResty.
