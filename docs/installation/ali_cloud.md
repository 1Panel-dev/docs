# Cloud Marketplace Deployment Guide
!!! note ""
    This guide explains how to purchase, deploy, and use the **1Panel** image through Alibaba Cloud Marketplace, and provides discount links for buying servers.

## 1 Purchase the Image
!!! note ""
    - 1Panel is available on Alibaba Cloud Marketplace. You can purchase it directly at:
      [Alibaba Cloud Marketplace · 1Panel Community Edition Image](https://market.aliyun.com/products/53690006/cmjj00071880.html?userCode=kmemb8jp)
    - You can also buy an Alibaba Cloud ECS instance and search for **1Panel** in the image list for quick deployment.

!!! note "Server Discount"
    If you do not have a server yet, you can purchase an Alibaba Cloud ECS instance using the following discount link:

    - [1Panel Exclusive Alibaba Cloud Discount – 30% OFF!](https://market.aliyun.com/common/dashi/1panel?userCode=kmemb8jp)

## 2 Open Ports
!!! note ""
    - To ensure external access to the 1Panel service, you must open port `8080` in your Alibaba Cloud ECS security group rules.
    - For detailed instructions, refer to Alibaba Cloud’s official guide:
      [How to Allow Ports in Security Groups](https://help.aliyun.com/document_detail/25471.html)

## 3 Usage Steps

### 3.1 Get Panel Credentials
!!! note ""
    - Run the command `1pctl user-info` to retrieve the default login information.
    - After executing the command, you will see the default username and password.

### 3.2 Access the Panel
!!! note ""
    - Visit the panel login page using this URL format:
      `http://<Server Public IP>:8090/panel`
    - Enter the default username and password you obtained.

### 3.3 Panel Setup
!!! note ""
    - For security purposes, we strongly recommend changing the default username and password immediately after your first login.
    - After completing the setup, you can start managing your server with 1Panel.
