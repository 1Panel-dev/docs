## 1 Install 1panel-migrator

### 1.1 Obtain the Installation Package
!!! note ""

    Please visit the [1Panel Gitee Release Page](https://gitee.com/fit2cloud-feizhiyun/1panel-migrator/releases/) to manually download the installation package matching your server architecture, then place it in the `/tmp` directory.

    **Note**: Ensure the package version is **v2.0.8 or higher** — only versions from v2.0.8 onward support master-slave node switching.

    Installation packages for the following architectures are provided for each release (filename examples):
    - `1panel-migrator-linux-amd64`
    - `1panel-migrator-linux-arm64`
    - `1panel-migrator-linux-arm`
    - `1panel-migrator-linux-ppc64le`
    - `1panel-migrator-linux-s390x`

### 1.2 Installation Steps

!!! note ""

    The following steps use the amd64 architecture as an example:

    ```bash
    # (1) Navigate to the temporary directory
    cd /tmp
    
    # (2) Add executable permissions
    chmod +x 1panel-migrator-linux-amd64
    
    # (3) Move to system PATH and rename
    mv 1panel-migrator-linux-amd64 /usr/local/bin/1panel-migrator
    ```

## 2 Slave Node → Master Node

!!! note ""

    To promote a slave node to master, you must first configure master node backups on the original master node — only master nodes with existing backup files support promotion:

    (1) Open the node list and click **Backup Master Node** at the top.
    
    (2) Select the nodes to back up, set the automatic backup frequency and retention count, then save the settings.
    
    (3) Click **Execute Backup** and check the backup result.

    ![img.png](../../img/installation/master_backup.png)

    (4) Open the slave node to be promoted, and run the promotion command with the installed 1panel-migrator:  
    `1panel-migrator promote`.

    ![img.png](../../img/installation/promote.png)

## 3 Master Node → Slave Node

!!! note ""

    Open the master node to be demoted, and run the demotion command with the installed 1panel-migrator:  
    `1panel-migrator demote`.

    ![img.png](../../img/installation/demote.png)
