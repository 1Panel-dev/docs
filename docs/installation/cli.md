
## 1 1pctl

!!! Abstract ""
    1Panel 默认内置了命令行运维工具 **1pctl**，通过执行 1pctl help，可以查看相关的命令说明。

    ```
    Usage:
      1pctl [COMMAND] [ARGS...]
      1pctl --help
    
    Commands: 
      status              查看 1Panel 服务运行状态
      start               启动 1Panel 服务
      stop                停止 1Panel 服务
      restart             重启 1Panel 服务
      uninstall           卸载 1Panel 服务
      user-info           获取 1Panel 用户信息
      version             查看 1Panel 版本信息
      reset               重置 1Panel 系统信息
    ```

## 2 1pctl reset

!!! Abstract ""
    **重置 1Panel 系统信息，包括取消安全入口登录，取消两步验证等**

    ```
    Usage:
      1pctl reset [COMMAND] [ARGS...]
      1pctl reset --help
    
    Commands: 
      domain              取消 1Panel 访问域名绑定
      entrance            取消 1Panel 安全入口
      https               取消 1Panel https 方式登录
      ips                 取消 1Panel 授权 IP 限制
      mfa                 取消 1Panel 两步验证
    ```

## 3 1panel app

!!! Abstract ""
    **应用商店相关命令，包括初始化应用等**

    ```
    Usage:
      1panel app [COMMAND] [ARGS...]
      1panel app --help
    
    Commands: 
      init                初始化应用
    ```

> 创建应用名为 `app_name`，版本为 `v1.0.0` 的应用，命令如下：

```shell
1panel app init -k app_name -v v1.0.0
```