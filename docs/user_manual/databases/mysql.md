## 1 管理数据库实例

1.1 应用商店安装数据库

!!! note ""
    通过应用商店安装的 MySQL、MariaDB 数据库应用，会自动出现在数据库实例列表中。

1.2 远程服务器

!!! note ""
    除应用商店安装的本地数据库以外，还可以添加已存在的数据库服务地址。点击列表上方的【远程服务器】按钮，即可进入远程服务器管理页面。

![img.png](../../img/databases/mysql_remote.png)

![img.png](../../img/databases/mysql_remote_add.png)

1.3 切换数据库实例

!!! note ""
    点击数据库列表上方的下拉菜单，即可在不同的数据库实例间进行切换，管理不同数据库实例下的数据库及设置等。

![img.png](../../img/databases/mysql_select.png)

## 2 创建数据库

!!! note ""
    创建一个新的数据库，首先输入数据库名称，选择编码格式，输入密码，设置访问权限，即可成功创建一个数据库。

![img.png](../../img/databases/create_mysql_db.png)

!!! note ""
    - 数据库名：新建数据库的名称，选择编码格式，默认为 UTF-8 格式。
    - 用户名：访问该数据库的用户名。
    - 密码：默认为随机密码，需要可以自行修改。
    - 访问权限：默认权限本地服务器权限，选项有:本地服务器，所有人，指定 IP。

## 3 查看连接信息

!!! note ""
    点击列表上方的【连接信息】按钮，即可查看数据库的地址、端口及 root 密码等连接信息，同时可以在这里修改数据库 root 密码。

![img.png](../../img/databases/mysql_connect.png)

!!! note "注意"
    应用商店部署的数据库采用容器化方式运行，不同的场景需要根据页面提示选择对应的连接信息。

## 4 从服务器同步

!!! note ""
    当使用了其他数据库工具或应用程序操作了数据库，数据库列表信息与实际不一致时，可以点击列表上方的【从服务器同步】按钮，主动从数据库查询当前数据库列表。

## 5 WEB 管理工具

!!! note ""
    如果需要使用 WEB 图形化界面管理 MySQL 数据库，可以列表上方的【管理】按钮，跳转到对应工具页面。

    目前支持的管理工具有：
    
    - [phpMyAdmin](https://www.wpdaxue.com/series/phpmyadmin)
    - Adminer

## 6 备份

!!! note ""
    点击备份列表按钮，选择备份，即可备份当前数据库文件。

![img.png](../../img/databases/backup_mysql_db.png)

!!! note ""
    - 默认数据库路径为 /opt/1panel/backup/database/mysql。
    - 备份使用 mysqldump 方式。

## 7 恢复

!!! note ""
    点击导入备份按钮，可以选择本地上传，或选择已备份的文件还原。

![img.png](../../img/databases/recover_mysql_db.png)

!!! note ""

    - 如从上传文件恢复，则需要保证上传文件压缩包内存在 test.sql 文件，否则无法正确导入。
    - 导入的 sql 文件格式必须符合标准，若你使用 phpmyadmin 导出的 sql 文件，可能会缺少版本 编码等信息，导致无法通过 mysqldump 正确导入。
    - 若无法正常导入，可以尝试使用 phpmyadmin 导入。

## 8 权限设置

!!! note ""
    点击操作列的【权限】按钮，可以修改指定数据库的访问权限，目前支持配置为所有人可访问或指定 IP 可访问。

![img.png](../../img/databases/update_mysql_db_access.png)

!!! note ""
    - 所有人：任何人都可以远程连接至数据库。
    - IP 地址：仅限指定的 IP 访问，多个 IP 使用英文逗号分隔。
    - 若需要开启外网访问，仍需要在防火墙中放行 MySQL 端口（默认3306）。

## 9 修改密码

!!! note ""
    - 修改当前的数据库账号的密码。
    - **注意事项：** 当前修改的密码为非 root 密码。

## 10 数据库配置

!!! note ""
    点击状态栏设置按钮，即可进入数据库具体设置界面，具体包括配置修改、当前状态、性能调整、端口、日志、慢日志。
    其中配置界面可对数据库配置进行手动调整。

![img.png](../../img/databases/mysql_conf.png)

!!! note ""
    - 系统 MySQL 使用 Docker 安装，配置文件默认挂载在 /opt/1panel/apps/mysql/[数据库名称]/conf/my.cnf。
    - **注意事项：** 错误的数据库配置将导致 MySQL 服务不可用，请谨慎修改。
    - 如数据库配置不正确导致服务无法正常启动，可尝试恢复默认配置后保存。

## 11 当前状态

!!! note ""
    当数据库查询缓慢时，可在数据库设置界面，点击当前状态按钮，查看当前数据库包括缓存命中数、索引命中数等各个常用指标的状态，通过这些状态对数据库进行性能优化。

![img.png](../../img/databases/mysql_status.png)

## 12 性能调整

!!! note ""
    系统支持表单方式直接调整数据库性能相关参数名，如索引缓冲区、连接数等，并且预设常用的优化方案，用户可根据系统环境，直接选择优化方案。

![img.png](../../img/databases/mysql_variables.png)

## 13 端口

!!! note ""
    除了在用户安装 MySQL 应用时可自由选择端口外，设置界面也可以直接进行端口的修改操作。

## 14 日志

!!! note ""
    - 系统 MySQL 使用 Docker 安装，本处产生日志为对应 MySQL 容器产生的日志。支持时间段筛选、追踪及下载操作。
    - 设置界面还支持查看 MySQL 产生的慢日志。

![img.png](../../img/databases/mysql_log.png)
