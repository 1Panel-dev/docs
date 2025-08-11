!!! note ""

    进入已安装列表，用户可以对应用进行同步、升级、重启、启动、停止、删除、备份和恢复等操作。

![img.png](../../img/app/installed_list.png)
{: .browser-mockup}

## 1 同步

!!! note ""

    点击【同步】按钮，可自动更新应用状态，确保与当前系统状态保持一致。

![img.png](../../img/app/app_sync.png)
{: .browser-mockup}

## 2 重建

!!! note ""

    点击【重建】按钮，系统会删除现有的应用实例，并基于当前的设置和配置重新安装和启动应用。

![img.png](../../img/app/app_rebuild.png)
{: .browser-mockup}

!!! tip "提示"

    重建应用会删除应用容器重新创建，配置了持久化的应用数据将会保留，如果有直接修改应用容器内其它文件，对应的修改内容将会被重置。

## 3 启动 / 停止 / 重启

![img.png](../../img/app/app_restart.png)
{: .browser-mockup}

## 4 卸载

!!! note ""

    点击【卸载】按钮，系统将自动执行卸载过程，删除应用的所有相关资源，包括容器、配置文件等。
    
    - 强制删除：会忽略删除过程中产生的错误并最终删除元数据。
    - 删除备份：删除备份列表中的备份文件。

![img.png](../../img/app/app_delete.png)
{: .browser-mockup}

## 5 应用详情

!!! note ""

    点击【参数】按钮，可以查看并修改应用的相关参数。

![img.png](../../img/app/install_detail.png)
{: .browser-mockup}

!!! note ""

    点击参数页面右上角的【编辑】按钮，可以对部分应用参数及应用高级设置进行修改，具体支持修改的参数与应用定义有关。

![img.png](../../img/app/app_modify.png)
{: .browser-mockup}

## 6 备份 / 恢复

!!! note ""

    点击【备份】按钮，进入备份列表。

![img.png](../../img/app/app_backup.png)
{: .browser-mockup}

!!! note ""

    点击【备份】按钮可立即备份当前应用。若需恢复应用，点击备份列表中的【恢复】按钮，将根据选定的备份恢复应用到相应状态。

![img.png](../../img/app/app_restore.png)
{: .browser-mockup}

!!! note ""

    也可将备份文件下载后，通过导入备份功能上传备份文件并进行恢复。

![img.png](../../img/app/backup_import.png)
{: .browser-mockup}

## 7 升级

!!! note ""

    进入【可升级】页面，可查看当前支持升级的应用。

![img.png](../../img/app/upgrade_list.png)
{: .browser-mockup}

!!! note ""

    点击应用卡片上的【忽略升级】按钮，可以不再显示该应用的升级提示。可以通过点击列表上方的【查看忽略应用】查看所有已忽略升级的应用并取消忽略。

![img.png](../../img/app/upgrade_ignore.png)
{: .browser-mockup}

!!! note ""

    点击【升级】按钮后，选择目标版本。可选择在升级前备份应用、自动拉取最新镜像、以及自定义修改 compose.yml 文件等。最后点击【确认】按钮，等待升级完成。

![img.png](../../img/app/app_upgrade.png)
{: .browser-mockup}
