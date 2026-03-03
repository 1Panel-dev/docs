!!! note ""
    Configure WAF for the website.

## 1 CC Protection

!!! note ""
    Configure CC Protection by filling in the following information:

    - Period: Detection period for CC Protection
    - Frequency: Frequency threshold for CC Protection

    Example: Period 60, Frequency 100 means if the same URL receives more than 100 requests within 60 seconds, CC Protection is triggered and the IP is blocked.

![img.png](../../img/websites/waf_cc.png)

## 2 IP Whitelist

!!! note ""
    Set an IP whitelist for website access.

![img.png](../../img/websites/ip_white.png)

## 3 IP Blacklist

!!! note ""
    Set an IP blacklist to block website access.

![img.png](../../img/websites/ip_black.png)

## 4 URL Whitelist

!!! note ""
    Set a URL whitelist for website access.

![img.png](../../img/websites/url_white.png)

## 5 URL Blacklist

!!! note ""
    Set a URL blacklist to block website access.

![img.png](../../img/websites/url_black.png)

## 6 Cookie Blacklist

!!! note ""
    Set a blacklist for forbidden data in cookies.

![img.png](../../img/websites/cookie_black.png)

## 7 GET Parameter Validation

!!! note ""
    Set forbidden parameters in GET requests.

![img.png](../../img/websites/get_check.png)

## 8 POST Parameter Validation

!!! note ""
    Set forbidden parameters in POST requests.

![img.png](../../img/websites/post_check.png)

## 9 File Extension Blacklist

!!! note ""
    File types that are forbidden from being uploaded.

![img.png](../../img/websites/ext_block.png)
