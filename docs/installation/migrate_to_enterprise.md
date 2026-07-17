---
title: 1Panel 迁移至企业版
description: 介绍使用 1panel-migrator 将 1Panel 社区版或专业版迁移至企业版的方法。
keywords: 1Panel 企业版,1panel-migrator,1Panel 社区版迁移,1Panel 专业版迁移,迁移至企业版
schema_type: TechArticle
---

本文适用于将 1Panel 社区版或专业版迁移至企业版。企业版的全新安装与版本升级请参考[企业版安装部署](enterprise_installation.md)。

## 1 获取迁移工具

!!! note ""
    请根据服务器架构，从以下任一发布页面下载对应的迁移工具：

    - [Gitee Releases](https://gitee.com/fit2cloud-feizhiyun/1panel-migrator/releases)
    - [GitHub Releases](https://github.com/1Panel-dev/1panel-migrator/releases)

## 2 迁移前准备

!!! note ""
    执行迁移前，需先将 1Panel 企业版安装包下载到当前 1Panel 所在服务器。企业版安装包需要放置在与当前 1Panel 安装目录同级的位置。

    示例：

    ```
    /opt/
    ├── 1panel/
    └── 1panel-v2.2.3-linux-amd64.tar.gz
    ```

## 3 执行迁移

!!! note ""
    执行以下命令，将当前 1Panel 迁移至企业版：

    ```bash
    1panel-migrator upgrade enterprise
    ```

    执行后，根据终端提示信息操作即可完成迁移。

## 4 注意事项

!!! note ""
    - 请根据服务器架构下载对应的迁移工具。
    - 迁移前需要提前下载 1Panel 企业版安装包。
    - 企业版安装包需要放置在与当前 1Panel 安装目录同级的位置。
    - 迁移前建议先确认当前版本是否在支持范围内。
