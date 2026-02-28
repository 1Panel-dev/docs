
## 1 1pctl

!!! note ""
    1Panel 默认内置了命令行运维工具 **1pctl**，通过执行 1pctl help，可以查看相关的命令说明。

    ```
    Usage:
      ./1pctl [COMMAND] [ARGS...]
      ./1pctl --help

    Commands:
      status [core|agent]         检查 1Panel 服务状态
      start [core|agent|all]      启动 1Panel 服务
      stop [core|agent|all]       停止 1Panel 服务
      restart [core|agent|all]    重启 1Panel 服务
      uninstall                   卸载 1Panel 服务
      user-info                   获取 1Panel 用户信息
      listen-ip                   切换 1Panel 监听 IP
      version                     查看 1Panel 版本信息
      update                      修改 1Panel 系统信息
      reset                       重置 1Panel 系统信息
      restore                     恢复 1Panel 服务及数据
    ```

## 2 1pctl 典型应用说明

### 2.1 1pctl reset

!!! note ""
    **重置 1Panel 系统信息，包括取消安全入口登录，取消两步验证等**

    ```
    Usage:
      1panel reset [command]

    Available Commands:

      domain      取消 1Panel 访问域名绑定
      entrance    取消 1Panel 安全入口
      https       取消 1Panel https 方式登录
      ips         取消 1Panel 授权 IP 限制
      mfa         取消 1Panel 两步验证
    ```

### 2.2 1pctl listen-ip

!!! note ""
    **修改 1Panel 监听 IP**

    ```
    Usage:
      1pctl listen-ip [COMMAND] [ARGS...]
      1pctl listen-ip --help
    
    Commands: 
      ipv4                监听 IPv4
      ipv6                监听 IPv6
    ```

### 2.3 1pctl update

!!! note ""
    **修改 1Panel 系统信息**

    ```
    Usage:
      1pctl update [COMMAND] [ARGS...]
      1pctl update --help
    
    Commands: 
      username            修改面板用户
      password            修改面板密码
      port                修改面板端口
    ```