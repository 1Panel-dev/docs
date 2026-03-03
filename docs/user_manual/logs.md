## 1 Panel Logs

### 1.1 Operation Logs

!!! note ""
    Records user operations performed in 1Panel.

![Panel Logs - Operation Logs](../img/logs/面板日志-操作日志.png)
{: .original}

### 1.2 Access Logs

!!! note ""
    Records access logs to the 1Panel dashboard.

![Panel Logs - Access Logs](../img/logs/面板日志-访问日志.png)
{: .original}

### 1.3 System Logs

!!! note ""
    Records runtime logs of the 1Panel service, used by developers to quickly troubleshoot issues.

![Panel Logs - System Logs](../img/logs/面板日志-系统日志.png)
{: .original}

## 2 Login Logs

!!! note ""
    Mainly records server SSH login events, used to check for unauthorized logins and operations.

!!! note "Tip"
    Log content is read from the system SSH login files, usually located at
    `/var/log/secure` or `/var/log/auth.log`.

    To clear login logs, you can manually delete historical content in these files.

![Login Logs](../img/logs/登录日志.png)
{: .original}

## 3 Website Logs

!!! note ""
    Displays logs for websites created in 1Panel, including runtime logs and error logs,
    which can be used to troubleshoot website access issues.

![img.png](../img/logs/网站日志-运行日志.png)
{: .original}

![img.png](../img/logs/网站日志-错误日志.png)
{: .original}
