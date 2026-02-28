!!! note ""
    On the Installed list page, you can perform operations on applications including sync, upgrade, restart, start, stop, delete, backup, and restore.

![img.png](../../img/app/installed_list.png)
{: .browser-mockup}

## 1 Sync

!!! note ""
    Click the **Sync** button to automatically update the application status and keep it consistent with the current system state.

![img.png](../../img/app/app_sync.png)
{: .browser-mockup}

## 2 Rebuild

!!! note ""
    Click the **Rebuild** button. The system will delete the existing application instance and reinstall and start the application based on the current settings and configuration.

![img.png](../../img/app/app_rebuild.png)
{: .browser-mockup}

!!! tip "Tip"
    Rebuilding an application deletes and recreates the application container. Data for applications with persistent storage will be retained. Any direct modifications to other files inside the application container will be reset.

## 3 Start / Stop / Restart

![img.png](../../img/app/app_restart.png)
{: .browser-mockup}

## 4 Uninstall

!!! note ""
    Click the **Uninstall** button. The system will automatically perform the uninstallation process and delete all resources related to the application, including containers, configuration files, etc.

    - **Force Delete**: Ignores errors during deletion and permanently removes metadata
    - **Delete Backups**: Deletes backup files in the backup list

![img.png](../../img/app/app_delete.png)
{: .browser-mockup}

## 5 Application Details

!!! note ""
    Click the **Parameters** button to view and modify application-related parameters.

![img.png](../../img/app/install_detail.png)
{: .browser-mockup}

!!! note ""
    Click the **Edit** button in the upper right corner of the parameters page to modify partial application parameters and advanced settings. The modifiable parameters depend on the application definition.

![img.png](../../img/app/app_modify.png)
{: .browser-mockup}

## 6 Backup / Restore

!!! note ""
    Click the **Backup** button to enter the backup list.

![img.png](../../img/app/app_backup.png)
{: .browser-mockup}

!!! note ""
    Click the **Backup** button to back up the current application immediately. To restore the application, click the **Restore** button in the backup list to revert the application to the corresponding state using the selected backup.

![img.png](../../img/app/app_restore.png)
{: .browser-mockup}

!!! note ""
    You can also download the backup file, then upload and restore it using the **Import Backup** function.

![img.png](../../img/app/backup_import.png)
{: .browser-mockup}

## 7 Upgrade

!!! note ""
    Go to the **Upgradable** page to view applications that support upgrades.

![img.png](../../img/app/upgrade_list.png)
{: .browser-mockup}

!!! note ""
    Click the **Ignore Upgrade** button on the application card to hide upgrade notifications for that application. You can view all ignored applications by clicking **View Ignored Applications** above the list and cancel the ignore.

![img.png](../../img/app/upgrade_ignore.png)
{: .browser-mockup}

!!! note ""
    After clicking the **Upgrade** button, select the target version. You can choose to back up the application before upgrading, automatically pull the latest image, and customize the `compose.yml` file. Finally, click **Confirm** and wait for the upgrade to complete.

![img.png](../../img/app/app_upgrade.png)
{: .browser-mockup}
