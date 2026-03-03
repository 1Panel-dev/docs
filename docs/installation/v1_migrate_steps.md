!!! warning "Important Note"

    Due to significant architectural changes between V1 and V2, **direct online upgrade from V1 to V2 is NOT supported**.

    To ensure a safe and successful migration, please read the [Upgrade Instructions](v1_migrate.md) carefully before proceeding.

## 1 Install 1panel-migrator

### 1.1 Obtain Installation Package

!!! note ""

    Visit the [1Panel Gitee Release Page](https://gitee.com/fit2cloud-feizhiyun/1panel-migrator/releases/) to manually download the installation package matching your server architecture, then place it in the `/tmp` directory:

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

## 2 Upgrade Instructions

!!! note ""

    The upgrade process consists of two steps: **Upgrade Service** and **Upgrade Websites**.

    > Important: Complete the service upgrade first, then proceed with the website upgrade.

!!! note ""

    Service upgrade has two roles:
    
    - **Master Node**: Contains both `1panel-core` and `1panel-agent` services, exposes external ports, and supports browser access.
    - **Slave Node**: Only contains the `1panel-agent` service, no external ports exposed, managed via the **Node Management** page of the master node.

### 2.1 Upgrade to Master Node

!!! note ""

    - **Upgrade Service**
    
    ```bash
    1panel-migrator upgrade core
    ```

!!! note ""

    - **Upgrade Websites**
    
    > Important: Ensure the V2 service is running successfully before executing this command.
    
    ```bash
    1panel-migrator upgrade website
    ```

### 2.2 Upgrade to Slave Node

!!! note ""

    - **Upgrade Service**
    
    ```bash
    1panel-migrator upgrade agent
    ```

    - **Add Slave Node to Master Node**
    
    Go to the **Node Management** page of the master node and add this slave node. The system will automatically detect and process V1 historical data.

!!! note ""

    - **Upgrade Websites**
    
    ```bash
    1panel-migrator upgrade website
    ```

!!! warning "Important"

    After adding the slave node, run the website upgrade command **on the slave node server**.

## 3 Rollback Instructions

!!! note ""

    If issues occur during upgrade, you can roll back to the previous 1Panel V1 version.

    The rollback process also has two steps: **Rollback 1Panel Service** and **Rollback Websites**.

!!! warning "Important"

    Complete the service rollback first, then proceed with the website rollback.

### 3.1 Service Rollback

!!! note ""

    No distinction between master/slave nodes — run this command directly on the target server:
    
    ```bash
    1panel-migrator rollback service
    ```

### 3.2 Website Rollback

!!! note ""

    Run this command on the target server as well:
    
    ```bash
    1panel-migrator rollback website
    ```

!!! warning "Important"

    Ensure the V1 service is running successfully before executing this command.
