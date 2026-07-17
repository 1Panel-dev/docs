---
title: 1Panel 企业版安装部署
description: 介绍 1Panel 企业版安装部署、企业版之间升级，以及社区版和专业版迁移至企业版的入口。
keywords: 1Panel 企业版,1Panel 企业版安装,1Panel 企业版部署,1panel-migrator,1Panel 社区版迁移,1Panel 专业版迁移
schema_type: TechArticle
---

!!! note ""
    1Panel 企业版是轻量级 AI 管理平台，可帮助企业实现从底层硬件到智能体（Metal-to-Agent）的统一管理。更多信息请参考 [1Panel 企业版](https://1panel.cn/enterprise.html)。

## 1 企业版概览

![1Panel 企业版功能架构](../img/installation/enterprise_architecture.svg)
{: .original}

## 2 获取企业版安装包

!!! note ""
    如需获取 1Panel 企业版安装包，请先[申请试用](https://jsj.top/f/umuYtv)。

## 3 安装与升级

!!! note ""
    获取企业版安装包后，将安装包上传至目标服务器并完成解压。安装包中包含 `install.sh` 和 `upgrade.sh` 两个脚本，进入解压后的安装包目录后，可根据实际场景执行相应脚本：

    - 首次安装 1Panel 企业版时，执行 `install.sh` 脚本。
    - 企业版之间升级时，执行 `upgrade.sh` 脚本。

    > `upgrade.sh` 仅适用于企业版之间的升级。

    > 社区版或专业版迁移至企业版时，请使用 **1panel-migrator** 工具，具体操作请参考[迁移至企业版](migrate_to_enterprise.md)。

## 4 社区版 / 专业版迁移至企业版

!!! note ""
    社区版或专业版迁移至企业版不适用 `upgrade.sh` 脚本，请参考[迁移至企业版](migrate_to_enterprise.md)完成迁移。
