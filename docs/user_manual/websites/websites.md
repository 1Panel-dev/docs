---
title: 1Panel 网站管理概述
description: 介绍 1Panel 支持的网站类型、网站列表信息和网站管理入口，帮助选择合适的部署方式。
keywords: 1Panel 网站管理,网站部署,OpenResty,运行环境,反向代理,静态网站
schema_type: TechArticle
---

# 网站概述

!!! note ""
    网站功能基于应用商店安装的 OpenResty，统一管理 HTTP/HTTPS 网站和 TCP/UDP 代理。社区版、专业版和企业版均可使用；企业版用户还需要相应的网站查看或管理权限。

## 1 支持的网站类型
!!! note ""
    - 一键部署应用网站；
    - PHP、Java、Node.js、Go、Python 和 .NET 运行环境网站；
    - 反向代理和静态网站；
    - PHP 或静态网站的子网站；
    - TCP/UDP 代理。

    具体参数参见 [创建网站](./website_create.md)。

## 2 网站列表

!!! note ""
    列表支持按类型、分组和名称筛选，显示网站类型、目录、状态、协议和到期时间。可直接启动或停止 HTTP 网站，并进入配置、备份、恢复和删除操作；TCP/UDP 代理的状态和操作方式以页面显示为准。

<div class="browser-mockup" markdown>

![网站列表](../../img/websites/website.png)

</div>

页面还提供分组、网站默认设置和批量操作。多节点环境下，网站及其 OpenResty、目录和证书都属于当前节点，操作前应确认节点选择器。

!!! warning "依赖 OpenResty"
    停止、卸载或升级 OpenResty 会影响当前节点上的网站。执行 OpenResty 维护前，应确认网站备份、配置备份和回滚方案。
