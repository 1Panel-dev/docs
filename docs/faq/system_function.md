## 1 Using a self-built Nginx reverse proxy for 1Panel causes both host and container terminals to malfunction

!!! note ""
    **You need to add the following configuration to your Nginx configuration file:**

    ```nginx
    location / {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
    ```

> **Alternatively, you can directly create a reverse proxy website in the 1Panel system to achieve the above functionality.**
