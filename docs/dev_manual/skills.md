!!! note ""
    本文档介绍如何使用 `1Panel-skills` 技能包，将 1Panel 的运维能力接入 OpenClaw 等智能体平台。  
    项目仓库地址：<https://github.com/1Panel-dev/1Panel-skills>

## 1 功能概述

!!! note ""
    `1Panel-skills` 是一个面向 OpenClaw 等智能体平台的 1Panel 运维技能包，基于 TypeScript 实现。当前版本以查询、读取、状态检查类能力为主，同时已经为后续扩展创建、更新、删除、重启等写操作预留了接口定义。

    当前支持的能力包括：

    - **资源监控**：当前节点状态、仪表盘指标、CPU / 内存 Top 进程、监控历史、GPU 历史
    - **网站检查**：网站列表与详情、Nginx 配置、域名、HTTPS 配置、SSL 证书、网站日志
    - **应用检查**：应用市场、已安装应用状态、服务信息、端口与连接信息
    - **容器检查**：容器列表、状态、Inspect、资源统计、日志
    - **日志检查**：操作日志、登录日志、系统日志文件列表、通用日志文件读取
    - **定时任务检查**：定时任务列表与详情、下次执行预览、执行记录、记录日志
    - **任务中心检查**：任务中心记录与执行中数量
    - **节点检查**：节点列表、简化节点列表、节点选项、节点状态

## 2 模块说明

!!! note ""
    `1Panel-skills` 当前提供以下模块：

    | 模块 | 说明 |
    |------|------|
    | `monitoring` | 仪表盘指标、当前节点状态、Top 进程、监控历史、GPU 历史 |
    | `websites` | 网站列表/详情、配置读取、HTTPS 读取、证书读取、网站日志读取 |
    | `apps` | 应用市场读取、已安装应用状态检查、服务读取、端口与连接信息 |
    | `containers` | 容器列表、状态、Inspect、资源统计、日志读取 |
    | `logs` | 操作日志、登录日志、系统日志文件、通用日志读取 |
    | `cronjobs` | 定时任务列表/详情、下次执行预览、记录、记录日志、脚本选项 |
    | `task-center` | 任务中心记录与执行中数量 |
    | `nodes` | 节点列表、节点选项、简化节点列表、节点状态 |

## 3 环境要求

!!! note ""
    使用 `1Panel-skills` 之前，请确保满足以下条件：

    - 建议使用 Node.js 18 或更高版本
    - 有一个可访问的 1Panel 实例
    - 已获取可用的 1Panel API Key

## 4 配置 1Panel API

!!! note ""
    在使用 `1Panel-skills` 前，需要先在 1Panel 中开启 API 接口：

    1. 登录 1Panel。
    2. 进入 **设置** -> **API 接口**。
    3. 开启 API 接口。
    4. 复制 API Key。
    5. 测试时可将客户端 IP 加入白名单：
       - IPv4：`0.0.0.0/0`
       - IPv6：`::/0`

    1Panel API 鉴权依赖以下两个请求头：

    - `1Panel-Timestamp`
    - `1Panel-Token = md5("1panel" + API_KEY + TIMESTAMP)`

    关于签名规则与接口鉴权方式，可参考本章节中的 [API 接口](./api_manual.md) 文档。

## 5 接入智能体平台

!!! note ""
    `1Panel-skills` 可以作为技能包接入多种智能体平台。当前仓库中已经提供了 OpenClaw 相关的插件入口与目录约定，下面以 OpenClaw 为例说明安装方式。

    推荐使用本地符号链接方式安装：

    ```bash
    mkdir -p ~/.openclaw/skills
    ln -s /path/to/1Panel-skills ~/.openclaw/skills/openclaw-1panel
    ```

    仓库已经包含 `dist/` 下的预编译运行产物，正常使用时不需要先手动重新构建。

## 6 配置运行环境变量

!!! note ""
    安装完成后，需要为运行环境设置以下变量：

    ```bash
    export ONEPANEL_BASE_URL="http://192.168.1.2:9999"
    export ONEPANEL_API_KEY="你的 1Panel API Key"
    export ONEPANEL_TIMEOUT_MS="30000"
    export ONEPANEL_SKIP_TLS_VERIFY="false"
    ```

    参数说明：

    - `ONEPANEL_BASE_URL`：1Panel 面板访问地址
    - `ONEPANEL_API_KEY`：在 1Panel 中生成的 API Key
    - `ONEPANEL_TIMEOUT_MS`：请求超时时间，单位为毫秒
    - `ONEPANEL_SKIP_TLS_VERIFY`：是否跳过 TLS 证书校验

## 7 CLI 用法

!!! note ""
    `1Panel-skills` 同时提供本地 CLI，可直接发起签名请求或执行模块动作。

    查看支持的模块：

    ```bash
    node dist/scripts/cli.js modules
    ```

    查看某个模块的动作：

    ```bash
    node dist/scripts/cli.js actions monitoring
    ```

    发起原始签名请求：

    ```bash
    node dist/scripts/cli.js request GET /api/v2/dashboard/base/os
    ```

    执行模块化动作：

    ```bash
    node dist/scripts/cli.js run monitoring getCurrentNode
    node dist/scripts/cli.js run websites searchWebsites --input-json '{"page":1,"pageSize":20}'
    ```

    打印当前签名 Header：

    ```bash
    node dist/scripts/cli.js sign
    ```

## 8 平台集成说明

!!! note ""
    `1Panel-skills` 提供两个运行时入口，可用于接入不同的运行环境或智能体平台。

    - `dist/plugin.js`：OpenClaw 插件入口
    - `dist/scripts/cli.js`：可直接执行的本地签名 CLI

    其中：

    - 插件元数据定义在 `openclaw.plugin.json`
    - 编译后的插件入口通过 `package.json` 导出

## 9 开发说明

!!! note ""
    如果需要对技能进行二次开发，可使用以下命令：

    安装依赖：

    ```bash
    npm install
    ```

    类型检查：

    ```bash
    npm run typecheck
    ```

    仅在修改 TypeScript 源码后，才需要重新构建：

    ```bash
    npm run build
    ```

## 10 注意事项

!!! note ""
    - 不要将真实 API Key 提交到版本控制中
    - 如果返回 `{"code":401,"message":"API 接口密钥错误"}`，请优先检查 API Key 是否正确，以及 1Panel API 设置是否已经保存
    - 如果返回 IP 相关鉴权错误，请检查白名单配置以及智能体运行环境的真实出口 IP
    - 某些节点相关接口可能要求 1Panel Pro 或 XPack

## 11 参考信息

!!! note ""
    - GitHub 仓库：<https://github.com/1Panel-dev/1Panel-skills>
    - 开源协议：MIT
