# PostgreSQL

## Mange DB instance

### PostgreSQL instance from App Store

PostgreSQL database applications installed through the App Store will automatically appear in the database instance list.

### Remote PostgreSQL instance

Beyond the local database installed via the App Store, you can also add existing database addresses. By clicking the `Manage remote servers` button located at the top of the list, you will be directed to the remote server management page.

Here, you can bind a remote server by filling in the connection and authentication information.

### Switching Database Instances

By clicking the dropdown menu at the top of the database list, you can switch between different database instances, managing databases and settings under different instances.

## Creating a database

!!! node "Parameters"
    - Name: The name of the new database, supporting character encoding settings.
    - Username: The username for accessing the database.
    - Password: Defaults to a random password, which can be modified as needed.

## Connection information

Clicking the `View connection info` button at the top of the list allows you to view the database's address, port, and root password, and also modify the database root password.

!!! info "Info"
    Databases installed via the App Store operate within a container. Depending on the scenario, you must choose the appropriate connection information as prompted on the page.

## Sync with server

If the database list information does not match the actual situation, possibly due to the use of other database tools or applications, clicking the "Sync with Server" button at the top of the list initiates an active query of the current database list directly from the database instance.

## WEB UI

To manage PostgreSQL databases using a WEB UI, click the `PGAdmin4` button at the top of the list, which will redirect you to the corresponding tool page.

## Backup database

The backup operation in the operation column allows you to back up the current database content or manage existing backups.

!!! info "Info"
    - The default backup path is `/opt/1panel/backup/database/postgresql`.
    - Backups are performed using `pg_dump`.

## Restore from a backup

By clicking the import backup button, you can choose to upload locally or restore from an existing backup file.

!!! info "Info"

    - Ensure the `.sql` file is present in the uploaded archive when restoring from an uploaded file, as its absence will result in an unsuccessful import.

## Change permissions

Click the `Change permissions` button in the operation column to modify whether the user bound to the current database is a superuser.

## DB instance Operations

You can stop/start the current DB instance in the status bar. And by clicking the `Configure` button, you can access the specific database settings page, which encompasses configuration modification, port, logs, and slow logs.

### Configuration file

The configuration page enables manual adjustments to the database configuration.

!!! info "Info"
    For PostgreSQL installed through the App Store, the default configuration file is located at `/opt/1panel/apps/postgresql/[App name]/data/postgresql.cnf`.

!!! warning "Warning"
    - In the event of incorrect database configuration leading to service startup failures, attempt to restore the default configuration and save it.
    - It is crucial to exercise caution when modifying the database configuration, as incorrect settings can result in the PostgreSQL service becoming unavailable.

### Port

In addition to setting the port during PostgreSQL application installation, the `Port` page also allows for port modifications.
