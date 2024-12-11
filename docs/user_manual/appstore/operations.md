# App Operations

In the installed list, users can perform operations such as synchronization, restart, start, stop, deletion, backup, and recovery on applications.

The updates list allows you to view and upgrade installed applications with new versions available.

## Sync status

Click the `Sync` button to update the application status and ensure it is consistent with the current status.

## Rebuilding an App

Click the `Rebuild` button to delete the existing application instance, and reinstall and start the application based on the current settings and configurations.

## Start/Stop/Restart

## Uninstalling an App

Click the `Uninstall` button to delete the existing application instance. All relevant resources associated with the application will be deleted, including containers and configuration files.

!!! note "Additional options"
    - **Force delete**：force deletion will ignore errors during the deletion process and eventually delete metadata.
    - **Delete backup**：delete the application backup files also.

## Editing an App

By clicking the `Edit parameters` button, you can view and edit the application's related parameters.

Click the `Edit` button in the upper right corner of the parameter page to modify some application parameters and advanced settings. 

!!! note "Note"
    The specific parameters that can be modified depend on the application definition.

## Backup and restore

By clicking the `Backup` button, you will enter the backup list. Click the `Backup` button to immediately back up the current application. 

If you need to restore the application, click the `Restore` button in the backup list, and the application will be restored to the corresponding state according to the selected backup.

## Updating an App

Access the `Updates` page to view the applications that are currently eligible for upgrade.

After clicking the `Upgrade` button, select the target version. You can choose to back up the application before upgrading, pull the latest image, and customize the `docker-compose.yml` file, among other options. Finally, click the `Confirm` button and wait for the upgrade to complete.
