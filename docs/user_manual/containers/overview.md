---
title: 1Panel 容器概览与 Docker 配置
description: 介绍 1Panel 容器概览中的运行状态、磁盘占用信息及 Docker 服务配置入口。
keywords: 1Panel 容器管理,Docker 概览,Docker 磁盘占用,Docker 配置,容器状态
schema_type: TechArticle
---

# 容器概览

!!! note "功能说明"
    容器概览汇总当前节点的 Docker 状态和资源数量。社区版、专业版和企业版均可使用；页面数据和操作对象始终属于当前所选节点。

    页面展示容器及其运行状态、编排、编排模板、镜像、镜像仓库、网络和存储卷数量，点击数量可进入对应列表。

<div class="browser-mockup" markdown>

![容器概览](../../img/containers/container_overview.png)

</div>

## 磁盘占用

!!! note ""
    磁盘占用区域分别展示镜像、容器、存储卷和构建缓存的使用量及可回收空间。点击 **清理** 会删除 Docker 判定为未使用的资源。

!!! warning "清理资源"
    清理前应确认停止的容器、未挂载存储卷、旧镜像和构建缓存不再需要。存储卷可能包含业务数据，不能只根据“未使用”状态判断是否可以删除。

## Docker 配置

!!! note ""
    页面还展示 Docker Socket 路径和镜像加速地址，并提供进入 Docker 配置页的入口。Docker 未安装、未启动或连接失败时，应先按页面状态提示处理，再使用其他容器功能。
