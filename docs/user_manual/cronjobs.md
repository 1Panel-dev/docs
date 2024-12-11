# Cron Jobs

## Summary

This feature is mainly used to manage tasks that need to be executed regularly, such as running a shell script, regular backup, regular URL access, etc., and also supports manual execution.

## Task Types

### Shell

!!! info "Configuration Description"
    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Execute in Container: After checking, you can select a container and execute the specified script in the container;
    - Script Content: The specific script content that needs to be executed;
    - Retention Copies: The number of retention copies of execution records and execution logs, the default is 7 copies;

### Backup App

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Application: Select the application that needs to be backed up, you can choose to back up a specific application, or back up all applications;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;
    - Exclusion Rules: The files that need to be excluded in the backup data compression package, such as log files, temporary directories, etc., support the configuration of multiple exclusion rules;

### Backup website

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Website: Select the website that needs to be backed up, you can choose to back up a specific website, or back up all websites;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;
    - Exclusion Rules: The files that need to be excluded in the backup data compression package, such as log files, temporary directories, etc., support the configuration of multiple exclusion rules;

### Backup database

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Database: Select the database that needs to be backed up, you can choose to back up a specific database, or back up all databases;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;
    - Exclusion Rules: The files that need to be excluded in the backup data compression package, such as log files, temporary directories, etc., support the configuration of multiple exclusion rules;

### Backup directory

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Directory: Select the directory that needs to be backed up;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;
    - Exclusion Rules: The files that need to be excluded in the backup data compression package, such as log files, temporary directories, etc., support the configuration of multiple exclusion rules;

### Backup logs

Backup the following log content:

- 1Panel System Log
- Server SSH Login Log
- All Website Logs

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;

### Access URL

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Retention Copies: The number of retention copies of execution records and execution logs, the default is 7 copies;
    - URL Address: The URL address that needs to be accessed regularly;

### Cut Website Logs

When the scheduled task is executed, it will split the logs of the specified website and save the previously generated logs in the backup directory.

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Website: Select the website that needs to be split, you can choose a specific website, or choose all websites;    
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;

### Cache Clean

Execute the `Cache clean` task in the `Toolbox` menu of the panel.

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Retention Copies: The number of retention copies of execution records and execution logs, the default is 7 copies;

### System snapshot

Execute the [`Create Snapshot`](../settings/#5) task in the `Settings`-`Snapshots` menu of the panel.

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Backup Account: The location where the backup data is stored, it can be saved on the current server disk, or in the object storage, FTP and other external storage services configured in the panel;
    - Compression Password: The protection password of the backup data compression package;
    - Default Download Address: When multiple backup accounts are selected, it is used as the default backup account when downloading backup files;
    - Retention Copies: The default is to save 7 copies, which can reduce the space used by the backup;
    - Exclusion Rules: The files that need to be excluded in the backup data compression package, such as log files, temporary directories, etc., support the configuration of multiple exclusion rules;

### Time Synchronization

Synchronize the time with the NTP server configured on the `Quick settings` page of the `Toolbox`.

!!! info "Configuration Description"

    - Execution Period: Select the execution time of the current scheduled task, and you can configure multiple execution periods at the same time;
    - Retention Copies: The number of retention copies of execution records and execution logs, the default is 7 copies;

## Execution Report

Display all the report details generated by this task, support time and status filtering, and if the scheduled task is a backup, you can directly download the report details through the download button.
