---
title: 1Panel 企业版离线安装
description: 介绍 1Panel 企业版离线安装包的获取、安装与升级，支持 7 天免费试用全部企业版功能，以及社区版和专业版迁移至企业版的入口。
keywords: 1Panel 企业版离线安装,1Panel 企业版,1Panel 企业版安装,1Panel 企业版免费试用,x86_64,amd64,aarch64,arm64,1panel-migrator
schema_type: TechArticle
---

!!! note ""
    🎉 **1Panel 离线安装包为企业版，支持 7 天免费试用，试用期间可体验全部企业版功能。**

    1Panel 企业版是轻量级 AI 管理平台，可帮助企业实现从底层硬件到智能体（Metal-to-Agent）的统一管理。更多信息请参考 [1Panel 企业版](https://1panel.cn/enterprise.html)。

## 1 企业版概览

![1Panel 企业版功能架构](../img/installation/enterprise_architecture.svg)
{: .original}

## 2 获取企业版离线安装包

!!! note ""
    请根据服务器架构获取对应的企业版离线安装包。安装后可免费试用 7 天，试用期间可体验全部企业版功能：

    - **x86_64（amd64）**：请前往 [FIT2CLOUD 开源社区下载页面](https://community.fit2cloud.com/#/products/1panel/downloads) 下载。该页面仅提供 x86_64（amd64）架构的安装包。
    - **aarch64（arm64）**：请填写 [1Panel 企业版试用申请表](https://jsj.top/f/umuYtv) 申请获取安装包。

## 3 安装与升级

!!! note ""
    获取对应架构的离线安装包后，将安装包上传至目标服务器并完成解压。安装包中包含 `install.sh` 和 `upgrade.sh` 两个脚本，进入解压后的安装包目录后，可根据实际场景执行相应脚本：

    - 首次安装 1Panel 企业版时，执行 `install.sh` 脚本。
    - 企业版之间升级时，执行 `upgrade.sh` 脚本。

    > `upgrade.sh` 仅适用于企业版之间的升级。

    > 社区版或专业版迁移至企业版时，请使用 **1panel-migrator** 工具，具体操作请参考[迁移至企业版](migrate_to_enterprise.md)。

## 4 社区版 / 专业版迁移至企业版

!!! note ""
    社区版或专业版迁移至企业版不适用 `upgrade.sh` 脚本，请参考[迁移至企业版](migrate_to_enterprise.md)完成迁移。
