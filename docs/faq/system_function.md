## 1 Using a self-built Nginx reverse proxy for 1Panel causes both host and container terminals to malfunction

!!! note ""
    **You need to add the following configuration to your Nginx configuration file:**

    ```nginx
    location / {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $http_host;
    }
    ```

    `proxy_set_header Host $http_host;` forwards the client's original Host header (including the port) to 1Panel. 1Panel validates that the Origin and Host of terminal WebSocket connections match; if the original Host is not forwarded, the validation fails with HTTP 403 and the terminal connection is interrupted. Use `$http_host` (which preserves the port) rather than `$host`.

    **Special case**: If the OpenResty version is `1.31.1.1-2-4-noble`, change the Host line in the configuration above to:

    ```nginx
    proxy_set_header Host $host$is_request_port$request_port;
    ```

> **Alternatively, you can directly create a reverse proxy website in the 1Panel system to achieve the above functionality.**
