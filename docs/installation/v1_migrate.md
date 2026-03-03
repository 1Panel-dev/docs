!!! note "Upgrade Notice"

    Due to significant architectural changes between V1 and V2, **direct online upgrade from V1 to V2 is NOT supported**.

    1Panel V1 users must use the official migration tool **1panel-migrator**:
    [1panel-migrator](https://gitee.com/fit2cloud-feizhiyun/1panel-migrator)
    to smoothly upgrade from 1Panel V1 to V2.

!!! warning "Important"
    To ensure a safe and successful migration, please read the following carefully before proceeding.

### 1 Create Snapshots

!!! note ""
    To prevent unexpected risks, it is **strongly recommended**:
    
    - Log into **1Panel → Panel Settings** and manually create a system snapshot.
    - Or create a snapshot of your cloud server via your cloud provider’s platform.

### 2 Version Requirements

!!! note ""

    - Migration is **only supported for 1Panel `v1.10.29-lts` and above**.
    - After migration, your system will be upgraded to **1Panel v2.0.0**.

### 3 Pro Edition & License

!!! note ""

    - Existing licenses will be cleared; all installations migrate to **Community Edition**.
    - V1 lifetime licenses cannot be used in V2 but can be upgraded at
      [Lingxia Official Site](https://www.lxware.cn/).
    - Before importing your license to V2, confirm it has been unbound at
      [Lingxia Official Site](https://www.lxware.cn/).

### 4 Data Update After Upgrade

#### 4.1 Websites

!!! note ""

    - **Website home directory migration**
    
      After migration, **all website configurations are stored under
      `{1Panel Install Dir}/www`**, e.g. `/opt/1panel/www`.

    - **OpenResty Version**
    
      The system will automatically upgrade to **OpenResty `1.27.1.2-0-1-focal`**.

    - **OpenResty Main Configuration**
    
      `1panel-migrator upgrade website` resets the main OpenResty config.
      **Back up your customizations first** if you have modified it.

    - **PHP Runtime Websites**
    
      1. Built-in PHP environments will be removed.
      2. **Existing PHP containers in websites will NOT be deleted**
         and will be migrated as static websites.
      3. You can later create V2 PHP environments and switch the migrated
         static site back to a PHP site in website settings.

    - **Reverse Proxy Websites**
    
      V2 redesigned the reverse proxy cache to use independent directories per site.
      **Please disable reverse proxy cache for all websites**
      before running `1panel-migrator upgrade website`.

#### 4.2 Backup Records

!!! note ""

    For compatibility reasons:
    - All **V1 website, app, and database backup records will be cleared**.
    - Please reconfigure your backup policies after migration.

#### 4.3 Host Terminal

!!! note ""

    Host list, groups, and quick commands are only migrated when upgrading to a **master node**.
    These data are **not migrated** for slave nodes.

#### 4.4 Cron Jobs

!!! note ""

    - Cron jobs **themselves are migrated**.
    - **Execution history will NOT be preserved**.

#### 4.5 Snapshots

!!! note ""

    Due to architectural changes, **V1 snapshots cannot be migrated to V2**.

#### 4.6 Panel Settings

!!! note ""

    After upgrade, panel settings for all nodes will follow the **V2 master node configuration**.

#### 4.7 WAF & Website Monitoring

!!! note ""

    Due to architecture upgrade:
    - Most **V1 WAF and website monitoring configurations are incompatible and will NOT be migrated**.
    - WAF only preserves: black/white lists, IP groups, custom rules.
    - Please reconfigure these features after migration.

#### 4.8 Feedback

!!! note ""

    If you encounter any issues or have feedback, please submit an Issue in the
    [1Panel main repository](https://github.com/1Panel-dev/1Panel/issues).