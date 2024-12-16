# Settings

## Panel settings

The panel settings view offers support for various fundamental panel settings, encompassing:

- Panel User: The 1Panel system only supports single-host single-user, and this is the validation information used to log in to the 1Panel panel, initialized by the user at the first login.
- Panel Password: The password used to log in to the 1Panel panel.
- Theme: The system supports light (light) and dark (dark) themes, which can be manually switched according to user habits, or can be selected to follow the system, automatically switching based on the theme mode used by the browser and operating system.
- Menu Tabs: After enabling, it will list the most recently visited menus at the top of the page through multiple tabs.
- Panel alias: Users can customize the panel name.
- Language: The system currently supports Chinese and English.
- Session timeout: This is the time after which the system automatically logs out if the user does not operate after logging in, with a minimum timeout time of 300 seconds.
- Server Address: Set the address of the current server, and after configuration, you can quickly open the service page of the specified application by clicking on the service port of the installed application in the app store.
- Enable API: Allow third-party applications to access the API.
- Preview program: After enabling, you can get the preview version of 1Panel to share feedback on new features and updates.

## Security

For users with high system requirements, we have introduced some advanced security settings, including:

- Panel Port: Modify the port used by the 1Panel service, but exercise caution to avoid conflicts with application ports that may prevent the service from starting. It is recommended to run `netstat -tunlp | grep [port]` before modifying the port to check if it is in use.
- Bind info: Modify the IP address that the 1Panel service listens on, with caution to ensure that the listening address does not prevent the current client from accessing the panel.
- Entrance: After enabling the secure entry, access to the panel is only possible through the specified secure entry, with support for configuring whether to enable related prompts.
- Unauthorized setting: Configure the content returned when accessing the panel without using a secure entry.
- Authorized IP: After setting authorized IPs, only the IPs listed can access the 1Panel service, supporting the configuration of multiple IP addresses.
- Bind domain: After setting domain binding, access to the 1Panel service is only possible through the domain name set.
- Panel SSL: Set HTTPS protocol access for the panel, enhancing the security of panel access. After enabling, access to the 1Panel service is only possible through HTTPS protocol.
- Expiration date: The system supports setting the number of days for password expiration, with a default of not set. When the password exceeds the expiration time, the system will redirect to the password change interface, requiring the modification of the account password, and the new password cannot be the same as the old password.
- Complexity validation: After enabling, the account password must be longer than 8 characters and contain numbers, letters, and special characters, such as Password@2023.
- Two-Factor Authentication: Enable MFA login verification, which requires scanning a QR code with a phone or browser after entering the username and password to complete the login, enhancing the system's security level.

!!! warning "Warning"
    Modifying the above settings may affect the way 1Panel services are accessed, potentially leading to issues with opening or logging into the 1Panel panel.

    In such cases, you can SSH into the server and use the `1pctl reset` and `1pctl update` commands to reset or update specific configurations.

    ```text
    root@hostname:/# 1pctl reset --help
    Reset system info

    Usage:
    1panel reset [command]

    Available Commands:

    domain      Cancel 1Panel domain binding
    entrance    Cancel 1Panel secure entrance
    https       Cancel 1Panel https login
    ips         Cancel 1Panel authorized ip restrictions
    mfa         Cancel 1Panel two-factor authentication

    Flags:
    -h, --help   help for reset

    Use "1panel reset [command] --help" for more information about a command.
    ```

    ```text
    root@hostname:/# 1pctl update
    Update panel info

    Usage:
    1panel update [command]

    Available Commands:

    password    Update panel password
    port        Update panel port
    username    Update panel user

    Flags:
    -h, --help   help for update

    Use "1panel update [command] --help" for more information about a command.
    ```

## Backup accounts

### Supported backup accounts

Supports the addition of local server disks and third-party accounts:

- AWS S3
- Alibaba Cloud OSS
- Tencent Cloud COS
- OneDrive
- Qiniu Kodo
- MINIO
- SFTP
- WebDAV

### Using your own client info for OneDrive

When adding OneDrive account, 1Panel defaults to using a unified Azure application information to call the OneDrive API. You can follow the steps below to create your own Azure application.

1. Access and log in to Microsoft Azure: https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade
2. Click on New Registration and fill in the registration information, where the Redirect URI serves as the Redirect URL parameter
3. The Application (Client) ID on the homepage serves as the Client ID
4. On the Certificates & Secrets page, create a new client secret, fill in the relevant information, and the generated value serves as the Client Secret
5. On the API Permissions page, select the required permissions, add permissions, Microsoft Graph, delegated permissions, and check Files.ReadWrite.All, offline_access, User.Read, which will be passed as the scope

### Auth code of OneDrive

You can follow the steps below to obtain the auth code for calling the OneDrive API.

1. Click the OneDrive authorization code `Acquire` button
2. Enter OneDrive account information
3. Trust the 1Panel service
4. Copy the authorization code from the address bar of browser into the 1Panel `Auth code` (note: do not include the &session_state=xxx part)

### Compatibility of Some Object Storage Service Providers with Amazon S3 Cloud Storage

|Provider|Documentation|Compatible Access Style|Compatibility|
| ------- | ------------ | --------------------- | ------------ |
|Cloudflare|Cloudflare S3 Compatibility API<br>[https://developers.cloudflare.com/r2/data-access/s3-api/](https://developers.cloudflare.com/r2/data-access/s3-api/)|Virtual Hosted Style / <br>Path Style|✅|
|Oracle Cloud|[https://docs.oracle.com/en-us/iaas/Content/Object/Tasks/s3compatibleapi.htm](https://docs.oracle.com/en-us/iaas/Content/Object/Tasks/s3compatibleapi.htm)|Virtual Hosted Style / <br>Path Style|✅|
|Self-built Minio|\-|Path Style|✅|

## Snapshots

Snapshots are used for full backups of the data generated by 1Panel, specifically including:

- Docker configuration files, located at /etc/docker/daemon.json;
- Applications in the app store, which can be viewed in the `App Store` - `Installed` section;
- Local backup data, which can be viewed in the `Settings` - `Backup Accounts` section;
- 1Panel-generated data, which compresses the entire `[Installation Directory]/1panel` directory, including database files;
- 1Panel binary files, located at `/usr/local/bin/1panel`;
- The 1pctl command-line tool, located at `/usr/local/bin/1pctl`;
- The 1panel.service file, located at `/etc/systemd/system/1panel.service`;

!!! tips "Tips"
    - Creating and syncing snapshots only supports selecting third-party accounts.
    - During the snapshot recovery process, a backup of the data before recovery will be performed, with the default backup path being [Installation Directory]/original_[snapshot name].
    - After a snapshot recovery failure, you can choose to troubleshoot the failure reason based on the [Panel Logs - System Logs], then retry the recovery, or directly roll back to the version before the recovery.
    - If the above operations cannot make the service run normally, you need to manually obtain the backup file before the recovery, manually replace the current system data, and then restart the system.
    - For operations such as machine migration, the snapshot needs to be placed in the specified directory of the corresponding backup account, such as the server disk: /opt/1panel/backup/system_snapshot/ .
