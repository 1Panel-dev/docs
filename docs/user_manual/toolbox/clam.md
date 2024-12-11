
# Virus Scan

## Introduction

1Panel uses [ClamAV](https://www.clamav.net/) for virus scanning. ClamAV is an open-source (GPLv2 licensed) antivirus toolkit specifically designed for scanning emails on mail gateways. It offers a variety of practical tools, including a flexible and extensible multi-threaded daemon, a command-line scanner, and advanced tools for automatically updating databases. The core of this toolkit is an antivirus engine provided in the form of a shared library.

## Requirement

The minimum recommended spec for ClamAV is

- CPU requirement: 1 CPU, 2.0 Ghz+;
- Memory requirement: 3 GiB+;
- Disk space: At least 5GiB of available disk space.

## Installing ClamAV

=== "RedHat / CentOS"
    1. Install the EPEL repository
    ```shell
    yum install -y epel-release
    ```
    2. Install ClamAV
    ```shell
    yum install -y clamav clamd clamav-update
    ```
    3. Modify the ClamAV configuration file by uncommenting the following lines in `/etc/clamd.d/scan.conf`.
    ```text
    LogFile /var/log/clamd.scan
    LogFileMaxSize 2M
    PidFile /run/clamd.scan/clamd.pid
    DatabaseDirectory /var/lib/clamav
    LocalSocket /run/clamd.scan/clamd.sock
    ```
    4. Modify the clamav-freshclam configuration file by uncommenting the following lines in `/etc/freshclam.conf`.
    ```text
    DatabaseDirectory /var/lib/clamav
    UpdateLogFile /var/log/freshclam.log
    PidFile /var/run/freshclam.pid
    DatabaseMirror database.clamav.net
    Checks 12
    ```
    5. Start the ClamAV service
    ```shell
    systemctl start clamd@scan.service
    systemctl start clamav-freshclam.service
    ```
    6. Enable ClamAV to start at boot
    ```shell
    systemctl enable clamd@scan.service
    systemctl enable clamav-freshclam.service
    ```
    7. Check the status of the ClamAV service
    ```shell
    systemctl status clamd@scan.service
    systemctl status clamav-freshclam.service
    ```

=== "Ubuntu / Debian"
    1. Install ClamAV
    ```shell
    sudo apt install clamav clamav-daemon -y
    ```
    2. Start the ClamAV service
    ```shell
    sudo systemctl start clamav-daemon
    sudo systemctl start clamav-freshclam.service
    ```
    3. Enable ClamAV to start at boot
    ```shell
    sudo systemctl enable clamav-daemon
    sudo systemctl enable clamav-freshclam.service
    ```
    4. Check the status of the ClamAV service
    ```shell
    sudo systemctl status clamav-daemon
    sudo systemctl status clamav-freshclam.service
    ```

## Scan task

When creating a scan task, you can specify the scan directory and the strategy for handling infected files.

The following handling strategies are currently supported for infected files after scanning:

- No action
- Delete the file
- Move the file to a quarantine directory
- Copy the file to a quarantine directory

!!! tip "Tips"
    By clicking the `Trigger` button in the operation column, you can manually execute the scan task. Clicking the `Records` button allows you to view the execution records and scan results of the scan task.