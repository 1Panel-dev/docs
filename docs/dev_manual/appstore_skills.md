---
title: 1Panel-appstore-skills 使用说明
description: 介绍使用 1Panel-appstore-skills 将官方 Docker 部署方案转换为 1Panel 应用商店安装包的方法。
keywords: 1Panel-appstore-skills,1Panel 应用商店,应用安装包,Docker Compose,AppSpec
schema_type: TechArticle
---

!!! note ""
    本文档介绍如何使用 `1panel-appstore-skills`，将已经支持 Docker 部署的应用转换为符合 1Panel 应用商店格式的应用安装包。
    项目仓库地址：<https://github.com/1Panel-dev/1Panel-appstore-skills>

## 1 功能概述

!!! note ""
    `1panel-appstore-skills` 可以根据应用官方仓库、官方文档、Docker 镜像、Compose 文件或中间 spec，整理应用元数据和容器部署参数，并生成 1Panel 应用包目录。

    该 Skill 主要处理以下内容：

    - 应用名称、版本、类型、标签、官网、文档和源码仓库；
    - 主服务及依赖服务的镜像、端口、环境变量、数据卷和启动依赖；
    - 1Panel 应用包所需的 `data.yml`、表单字段和多语言描述；
    - 中文 README，以及官方应用或文档支持英文时的英文 README；
    - 持久化目录需要权限初始化时使用的 `init.sh`。

    `1Panel-skills` 主要用于将 1Panel 运维查询能力接入智能体平台；`1panel-appstore-skills` 用于生成应用安装包，两者用途不同。

## 2 使用前提
!!! note ""
    - 本地已经安装 Python 3；
    - 应用具有可靠的 Docker 或 Docker Compose 部署方式；
    - 可以访问应用官方仓库、官方文档或官方镜像说明；
    - 使用前已按照智能体平台的 Skill 加载方式启用本仓库，并确保平台能够读取仓库根目录中的 `SKILL.md`。

    可以通过以下命令获取仓库：

    ```bash
    git clone https://github.com/1Panel-dev/1Panel-appstore-skills.git
    ```

    不同智能体平台的 Skill 安装目录和加载方式可能不同，应以对应平台的说明为准。

## 3 适用场景
!!! note ""
    适合使用该 Skill 的场景包括：

    - 将已经支持 Docker 部署的应用封装为 1Panel 应用商店应用；
    - 将官方仓库或官方文档中的 Docker / Docker Compose 安装方式转换为 1Panel 应用包；
    - 将现有 `docker-compose.yml` 整理为 1Panel 应用商店目录结构；
    - 根据准备好的 app spec 生成 `data.yml`、`docker-compose.yml`、README 和数据目录。

    以下场景不适合直接使用：

    - 应用没有可靠的 Docker 部署方式；
    - 镜像、端口、挂载目录、环境变量或运行用户需要依靠猜测；
    - 需要直接发布到远程应用商店仓库。该 Skill 只生成应用包，不执行远程发布。

## 4 支持的输入
!!! note ""
    | 输入类型 | 说明 |
    | --- | --- |
    | 应用名称 | Skill 会查找并确认应用官方仓库，再核对 Docker 部署方式 |
    | 官方仓库地址 | 以指定仓库作为主要信息来源 |
    | Docker 镜像 | 需要同时提供或从官方来源确认端口、环境变量和数据目录等参数 |
    | `docker-compose.yml` / `compose.yml` | 根据官方 Compose 配置整理服务拓扑和 1Panel 表单字段 |
    | 中间 spec | 使用符合 `references/appspec.md` 的 JSON 文件直接生成应用包 |

## 5 工作流程
!!! note ""
    1. 确认应用官方仓库或官方文档；
    2. 核对 Docker 镜像、服务、端口、环境变量、挂载目录、运行用户和依赖关系；
    3. 按 `references/appspec.md` 整理中间 JSON spec；
    4. 使用 `scripts/generate_app_package.py` 生成应用包；
    5. 使用校验脚本检查目录结构和基础字段；
    6. 将应用包放入 1Panel 本地应用目录，完成安装和生命周期测试。

!!! warning "信息来源"
    Docker 安装方式必须来自应用官方仓库或官方文档。优先使用官方镜像；只有官方没有公开镜像或仅提供源码构建方式，并且用户明确接受时，才可以使用来源清晰的第三方镜像。无法确认可靠容器化方案时，应停止生成应用包。

## 6 使用示例
!!! note ""
    提供官方仓库地址：

    ```text
    使用 1panel-appstore-skills，把 https://github.com/example/myapp 封装成 1Panel 应用商店应用。
    ```

    提供镜像和端口：

    ```text
    使用 1panel-appstore-skills，把 ghcr.io/example/myapp:1.0.0 封装成 1Panel 应用商店应用。
    主机端口为 8080，容器端口为 3000。
    ```

    使用当前目录中的 Compose 文件：

    ```text
    使用 1panel-appstore-skills，把当前目录的 docker-compose.yml 转成 1Panel 应用商店应用包。
    ```

## 7 根据 spec 生成应用包
!!! note ""
    已经准备好中间 spec 时，可以直接运行生成脚本：

    ```bash
    python3 scripts/generate_app_package.py \
    --spec assets/sample-appspec.json \
    --output apps
    ```

    默认生成目录结构如下：

    ```text
    apps/<app-key>/
    logo.png
    README.md
    README_en.md
    data.yml
    <version>/
        data.yml
        docker-compose.yml
        data/
        scripts/
    ```

    `scripts/` 为可选目录。只有官方来源能够证明持久化目录需要调整权限或存在必要的安装前操作时，才会生成 `scripts/init.sh`。

    生成后可以执行基础校验：

    ```bash
    python3 scripts/validate_app_package.py apps/<app-key>
    ```

!!! note "校验范围"
    校验脚本只检查应用包目录和基础字段，不能替代 `docker compose config`、镜像可用性检查以及真实安装、启动、停止、重启和卸载测试。

## 8 本地测试
!!! note ""
    将生成的应用目录复制到 1Panel 本地应用目录：

    ```text
    /opt/1panel/resource/apps/local/<app-key>
    ```

    进入 **应用商店 -> 本地应用**，刷新应用列表后进行安装测试。至少需要验证：

    - 应用表单可以正常提交；
    - Compose 配置能够正确解析；
    - 应用可以安装、启动、停止和重启；
    - 持久化数据在容器重建后仍然存在；
    - 卸载时的数据保留或删除行为符合页面选项；
    - 页面访问地址、端口和依赖服务正常。

!!! warning "敏感信息"
    不要把真实密码、Token、API Key 或私有仓库凭据写入 spec、README、`docker-compose.yml` 或示例文件。敏感参数应通过 `data.yml` 的密码字段由用户在安装时填写。
