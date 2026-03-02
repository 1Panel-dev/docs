## 1 s390x Architecture

### 1.1 Install MySQL

!!! note ""
    **MySQL does not provide official s390x images. You must manually change the MySQL image before installing it from the 1Panel App Store.**

!!! note "MySQL 5.7"

    - Pull the latest s390x image
    ```bash
    docker pull ibmcom/mysql-s390x:5.7.34
    ```
    - Tag it to match the version used in 1Panel App Store
    ```bash
    docker tag ibmcom/mysql-s390x:5.7.34 mysql:5.7.42
    ```
    - Install MySQL in the App Store and select version **5.7.42**

!!! note "MySQL 8.0"

    - Pull the latest s390x image
    ```bash
    docker pull ibmcom/mysql-s390x:8.0.25
    ```
    - Tag it to match the version used in 1Panel App Store
    ```bash
    docker tag ibmcom/mysql-s390x:8.0.25 mysql:8.0.33
    ```
    - Install MySQL in the App Store and select version **8.0.33**


## 2 armv7l Architecture

### 2.1 Install MySQL

!!! note ""
    **MySQL does not provide official armv7l images. You must manually change the MySQL image before installing it from the 1Panel App Store.**

!!! note "MySQL 5.7"

    - Pull the latest armv7l image
    ```bash
    docker pull biarms/mysql:5.7.33-beta-circleci
    ```
    - Tag it to match the version used in 1Panel App Store
    ```bash
    docker tag biarms/mysql:5.7.33-beta-circleci mysql:5.7.42
    ```
    - Install MySQL in the App Store and select version **5.7.42**

!!! note "MySQL 8.0"

    **MySQL 8.0 is not yet supported on armv7l in the current 1Panel version.**


### 2.2 Install OpenResty

!!! note ""
    **OpenResty does not provide official armv7l images. You must manually change the OpenResty image before installing it from the 1Panel App Store.**

!!! note ""

    - Pull the latest armv7l image
    ```bash
    docker pull imzcc/openresty:1.21.4.1-7-alpine
    ```
    - Tag it to match the version used in 1Panel App Store
    ```bash
    docker tag imzcc/openresty:1.21.4.1-7-alpine openresty/openresty:1.21.4.1-7-focal
    ```
    - Install OpenResty in the App Store
