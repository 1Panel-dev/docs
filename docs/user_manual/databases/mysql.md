# MySQL and MariaDB

## Mange DB instance

### MySQL/MariaDB instance from App Store

MySQL and MariaDB database applications installed through the App Store will automatically appear in the database instance list.

### Remote MySQL/MariaDB instance

Beyond the local database installed via the App Store, you can also add existing database addresses. By clicking the `Manage remote servers` button located at the top of the list, you will be directed to the remote server management page.

Here, you can bind a remote server by filling in the connection and authentication information.

### Switching Database Instances

By clicking the dropdown menu at the top of the database list, you can switch between different database instances, managing databases and settings under different instances.

## Creating a database

!!! node "Parameters"
    - Name: The name of the new database, supporting character encoding settings.
    - Username: The username for accessing the database.
    - Password: Defaults to a random password, which can be modified as needed.
    - Permissions: Defaults to local server permissions, with options including: all users, and specified IPs.

## Connection information

Clicking the `View connection info` button at the top of the list allows you to view the database's address, port, and root password, and also modify the database root password.

!!! info "Info"
    Databases installed via the App Store operate within a container. Depending on the scenario, you must choose the appropriate connection information as prompted on the page.

## Sync with server

If the database list information does not match the actual situation, possibly due to the use of other database tools or applications, clicking the "Sync with Server" button at the top of the list initiates an active query of the current database list directly from the database instance.

## WEB UI

To manage MySQL databases using a WEB UI, click the `Manage database` button at the top of the list, which will redirect you to the corresponding tool page.

!!! info "Supported management tools"
    - [phpMyAdmin](https://www.wpdaxue.com/series/phpmyadmin)
    - Adminer

## Backup database

The backup operation in the operation column allows you to back up the current database content or manage existing backups.

!!! info "Info"
    - The default backup path is `/opt/1panel/backup/database/mysql` or `/opt/1panel/backup/database/mariadb`.
    - Backups are performed using `mysqldump`.

## Restore from a backup

By clicking the import backup button, you can choose to upload locally or restore from an existing backup file.

!!! info "Info"

    - Ensure the `.sql` file is present in the uploaded archive when restoring from an uploaded file, as its absence will result in an unsuccessful import.
    - The imported SQL file must adhere to standard formatting. SQL files exported using phpMyAdmin may be missing version and encoding information, potentially causing issues with mysqldump imports.
    - If normal import attempts fail, consider using phpMyAdmin for the import process.

## Change permissions

Click the `Change permissions` button in the operation column to modify the access permissions for a specific database. Currently, you can configure access for all users or specific IPs.

## DB instance Operations

You can stop/start the current DB instance in the status bar. And by clicking the `Configure` button, you can access the specific database settings page, which encompasses configuration modification, current status, performance tuning, port, logs, and slow logs.

### Configuration file

The configuration page enables manual adjustments to the database configuration.

!!! info "Info"
    For MySQL/MariaDB installed through the App Store, the default configuration file is located at `/opt/1panel/apps/[mysql/mariadb]/[App name]/conf/my.cnf`.

!!! warning "Warning"
    - In the event of incorrect database configuration leading to service startup failures, attempt to restore the default configuration and save it.
    - It is crucial to exercise caution when modifying the database configuration, as incorrect settings can result in the MySQL service becoming unavailable.

### Current state

To address slow database queries, navigate to the `Current state` page, and review the status of key metrics such as cache hit rates and index hit rates to optimize database performance.

### Performance tuning

The system offers a form-based interface for directly adjusting database performance parameters, including index buffer and connection numbers. Furthermore, it provides pre-set optimization plans that users can choose based on their system environment.

### Port

In addition to setting the port during MySQL application installation, the `Port` page also allows for port modifications.
