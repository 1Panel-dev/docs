# 1pctl Command Line Tool

## 1 1pctl
!!! note ""
    1Panel comes with a built‑in command‑line tool **1pctl** for server maintenance.
    Run `1pctl help` to view all available commands.

    ```
    Usage:
      ./1pctl [COMMAND] [ARGS...]
      ./1pctl --help

    Commands:
      status [core|agent]         Check 1Panel service status
      start [core|agent|all]      Start 1Panel service
      stop [core|agent|all]       Stop 1Panel service
      restart [core|agent|all]    Restart 1Panel service
      uninstall                   Uninstall 1Panel
      user-info                   Show 1Panel user credentials
      listen-ip                   Switch 1Panel listening IP
      version                     Show 1Panel version
      update                      Modify 1Panel system settings
      reset                       Reset 1Panel system settings
      restore                     Restore 1Panel service and data
    ```

## 2 Typical Usage of 1pctl

### 2.1 1pctl reset

!!! note ""
    **Reset 1Panel system settings, such as disabling secure entrance, turning off 2FA, etc.**

    ```
    Usage:
      1pctl reset [command]

    Available Commands:

      domain      Remove domain binding
      entrance    Disable secure entrance
      https       Disable HTTPS login
      ips         Remove IP whitelist restriction
      mfa         Disable two-factor authentication
    ```

### 2.2 1pctl listen-ip

!!! note ""
    **Modify 1Panel listening IP**

    ```
    Usage:
      1pctl listen-ip [COMMAND]
      1pctl listen-ip --help

    Commands:
      ipv4        Listen on IPv4 only
      ipv6        Listen on IPv6 only
    ```

### 2.3 1pctl update

!!! note ""
    **Modify 1Panel system information**

    ```
    Usage:
      1pctl update [COMMAND]
      1pctl update --help

    Commands:
      username    Change panel username
      password    Change panel password
      port        Change panel port
    ```
