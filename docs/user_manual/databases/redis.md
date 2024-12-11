# Redis

## Mange Redis instance

### Redis instance from App Store

Redis database applications installed through the App Store will automatically appear in the redis instance list.

### Remote Redis instance

Beyond the local database installed via the App Store, you can also add existing redis addresses. By clicking the `Manage remote servers` button located at the top of the list, you will be directed to the remote server management page.

Here, you can bind a remote server by filling in the connection and authentication information.

### Switching Redis Instances

By clicking the dropdown menu at the top of the command line area, you can switch between different redis instances, managing settings under different instances.

## Connection information

Clicking the `View connection info` button at the top of the list allows you to view the redis database's address, port, and root password, and also modify the database root password.

!!! info "Info"
    Resi databases installed via the App Store operate within a container. Depending on the scenario, you must choose the appropriate connection information as prompted on the page.

## Redis instance Operations

You can stop/start the current Redis instance in the status bar. And by clicking the `Configure` button, you can access the specific redis settings page, which encompasses configuration modification, current status, performance tuning, port and data persistence.

### Configuration file

The configuration page enables manual adjustments to the database configuration.

!!! info "Info"
    For Redis installed through the App Store, the default configuration file is located at `/opt/1panel/apps/redis/[App name]/conf/redis.conf`.

!!! warning "Warning"
    - In the event of incorrect database configuration leading to service startup failures, attempt to restore the default configuration and save it.
    - It is crucial to exercise caution when modifying the database configuration, as incorrect settings can result in the Redis service becoming unavailable.

### Current state

To address slow database queries, navigate to the `Current state` page, and review the status of key metrics such as memory allocation and query hit rates to optimize database performance.

### Performance tuning

The system offers a form-based interface for directly adjusting database performance parameters.

### Port

In addition to setting the port during Redis application installation, the `Port` page also allows for port modifications.

### Persistence

Redis persistence is categorized into two primary types, AOF and RDB:

- RDB:
    - Implementation: When the parent process saves the RDB file, it first forks a child process, which then handles the subsequent saving work. The parent process does not need to perform any disk I/O operations.
    - Advantages: It saves the Redis dataset at a certain point in time in a file, suitable for disaster recovery, can maximize Redis performance, is faster, and is also faster when recovering large datasets.
    - Disadvantages: There is a risk of data loss, requiring the setting of backup frequencies. In the event of a failure shutdown, data may be lost, and when the dataset is large, forking a child process can be very time-consuming, causing service downtime.
- AOF:
    - Implementation: It appends operations to the log file either periodically or after each write command. The log file only performs append operations. When the AOF file becomes too large, it automatically rewrites the AOF, retaining only the minimum command set required to recover the current dataset.
    - Advantages: It sequentially saves all write operations executed on the database, making data loss less likely. Even in the event of a failure shutdown, only the data after the last write operation to the log file will be lost, making it more reliable and easier to analyze the file.
    - Disadvantages: For the same dataset, the AOF volume is generally larger, and the speed may be slower than RDB.
