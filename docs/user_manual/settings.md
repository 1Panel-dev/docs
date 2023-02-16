## 面板

!!! Abstract ""
    支持设置账号、主题、语言、服务器时间等信息

## 安全

!!! Abstract ""
    支持设置面板端口、密码过期时间、开启两步验证等

## 备份账号

!!! Abstract ""
    支持添加本地服务器磁盘和第三方账号

    第三方账号：

    - 亚马逊 S3 云存储
    - 阿里云 OSS
    - MINIO
    - SFTP

## 监控

!!! Abstract ""
    支持设置是否开启服务器监控和监控日志保留天数

## 快照

!!! Abstract ""

    快照用于全量备份 1Panel 所产生的数据，具体包括：
    
    - Docker 配置文件，路径为 /etc/docker/daemon.json；
    - Docker 数据，可在【容器 - 配置】中查看；
    - 本地备份数据，可在【面板设置 - 备份账号】中查看；
    - 1Panel 产生的数据，将压缩整个 [安装目录]/1panel 目录，包括数据库文件；
    - 1panel 二进制文件，路径为 /usr/local/bin/1panel；
    - 1pctl 命令行工具，路径为 /usr/local/bin/1pctl；
    - 1panel.service 路径为 /etc/systemd/system/1panel.service；

    创建和同步快照只支持选择第三方账号。

## 关于

!!! Abstract ""
    支持检查 1Panel 服务是否存在新版本
