!!! note ""
    AI 网关用于统一管理模型账号、调用凭证、访问配额和请求转发。客户端只需配置网关的外部连接地址和 API Key，即可通过统一入口调用不同供应商或本地部署的模型。

    进入 1Panel 面板后，打开 **AI -> AI 网关** 页面即可进行管理。

    该功能属于 [1Panel 企业版](https://1panel.cn/enterprise.html)。
!!! note ""
    新版 AI 网关包含 **账号池、模型组、API Key、用户组、智能路由、内容合规、用量统计、设置** 8 个功能入口。建议按照以下顺序完成首次配置：

    1. 在 **账号池** 中导入模型账号并配置模型映射。
    2. 按需创建 **模型组**，用于限制用户组可用模型或配置智能路由。
    3. 创建 **用户组**，设置 QPS、Token 配额和模型范围。
    4. 创建 **API Key**，交付给客户端使用。
    5. 按需启用智能路由、内容合规、用量统计和 Elasticsearch。

## 1 运行状态与基础操作

!!! note ""
    AI 网关页面顶部展示服务状态和外部连接地址，并提供以下操作：

    - **状态**：查看运行状态、服务自启、监听端口、负载策略、并发限制、超时参数、日志路径和 Elasticsearch 写入状态
    - **启动 / 停止 / 重启**：控制 AI 网关服务
    - **设置**：进入网关设置页面
    - **日志**：查看 AI 网关运行日志
    - **外部连接地址**：客户端配置的 Base URL，可直接复制

![AI 网关账号池](../../img/ai/ai_gateway_account_pool.jpg)
{: .browser-mockup}

## 2 账号池

!!! note ""
    **账号池** 用于维护 AI 网关的上游模型账号。点击 **导入模型账号**，选择已在 **AI -> 模型** 中创建的账号，并配置权重、优先级和模型映射。

    列表会展示模型供应商、API 类型、上游 API 地址、健康状态、失败次数和最近错误，便于检查账号是否可以正常参与转发。当前页面可同时管理 `openai-completions`、`openai-responses`、`anthropic-messages` 等不同 API 类型的模型账号。

!!! info "导入参数"
    - **模型账号**：选择已有模型账号
    - **权重**：负载策略使用权重时，权重越高承担的请求越多
    - **优先级**：负载策略使用优先级时，数值用于确定账号选择顺序
    - **模型映射**：将客户端请求模型映射到该账号的真实上游模型
    - **验证账号可用性**：保存前发送最小请求检查接口是否可用
    - **启用**：控制该账号是否参与网关转发

![导入模型账号](../../img/ai/ai_gateway_import_account.png)
{: .browser-mockup}

> 模型映射左侧填写客户端请求中的 `model`，右侧填写真实上游模型。客户端只需要感知映射后的请求模型名。

## 3 模型组

!!! note ""
    **模型组** 用于组合一组真实上游模型，主要应用于用户组模型权限和智能路由。创建模型组时填写名称、请求模型和备注；模型在组内的顺序表示智能路由的选择优先级，组内不进行模型间负载均衡。

    `auto` 是客户端触发智能路由时使用的虚拟模型名，不需要添加到模型组中。

![AI 网关模型组](../../img/ai/ai_gateway_model_groups.jpg)
{: .browser-mockup}

## 4 用户组

!!! note ""
    **用户组** 用于统一管理一组 API Key 的调用配额和模型范围。创建用户组后，再将 API Key 绑定到该用户组。

![AI 网关用户组](../../img/ai/ai_gateway_user_groups.jpg)
{: .browser-mockup}

!!! info "用户组参数"
    - **用户组**：用户组名称
    - **QPS 限制**：限制每秒请求数，`0` 表示不限制
    - **Token 限制**：限制该组可使用的 Token 配额，`0` 表示不限制
    - **模型组**：限制该组可以调用的模型；不选择时表示不限制
    - **状态**：禁用后，该组下的 API Key 无法继续调用
    - **备注**：记录部门、项目或使用场景

默认用户组不可删除。API Key 绑定用户组后，会继承用户组的 QPS、Token 配额和模型范围。

## 5 API Key

!!! note ""
    在 **API Key** 页面点击 **创建**，选择用户和用户组，确认系统生成的 API Key 后保存。列表会展示可用模型、QPS 限制、Token 用量、状态、最近使用时间等信息，并支持编辑、删除和重置 Token。

    API Key 只会在创建时完整展示，请妥善保存。重置 Token 后，原 Token 将无法继续使用，需要同步更新客户端配置。

![创建 API Key](../../img/ai/ai_gateway_api_key_create.png)
{: .browser-mockup}
!!! info "客户端调用示例"
    ```bash
    curl http://<服务器 IP>:4000/v1/chat/completions \
      -H "Authorization: Bearer <API Key>" \
      -H "Content-Type: application/json" \
      -d '{
        "model": "deepseek-v4-flash",
        "messages": [
          {
            "role": "user",
            "content": "Hello"
          }
        ],
        "stream": true
      }'
    ```

客户端应将页面顶部的 **外部连接地址** 作为 Base URL。`model` 可以填写账号池中的请求模型名；启用智能路由后，也可以填写 `auto`。

## 6 智能路由

!!! note ""
    智能路由根据请求复杂度，在简单模型组和复杂模型组之间选择模型。只有客户端请求使用 `model=auto` 时才会触发智能路由；请求其他模型名时，仍按普通 AI 网关流程转发。

![AI 网关智能路由](../../img/ai/ai_gateway_smart_routing.jpg)
{: .browser-mockup}

### 6.1 配置流程
!!! note ""
    1. 在 **模型组** 中分别创建简单模型组和复杂模型组，并配置真实上游模型。
    2. 在 **设置 -> Embedding** 中配置 Embedding 服务、路由阈值和 TopK。
    3. 在 **设置 -> 智能路由** 中启用功能，并选择简单模型组和复杂模型组。
    4. 在 **智能路由 -> 样本** 中维护简单、复杂请求样本，并生成或重建向量。
    5. 客户端使用 `model=auto` 发起请求。

### 6.2 功能说明

!!! info "样本"
    样本用于描述简单或复杂问题。列表展示标签、样本文本、向量模型和向量维度，新增或调整 Embedding 配置后可以点击 **重建向量**。
![智能路由样本](../../img/ai/ai_gateway_smart_routing_sample.png)
{: .browser-mockup}
!!! info "预览"
    输入一段请求文本，查看它会被判定为简单还是复杂，并显示判定来源。预览只执行路由判断，不会真实调用上游模型。
![智能路由预览](../../img/ai/ai_gateway_smart_routing_sample_yulan.png)
{: .browser-mockup}
!!! info "决策日志"
    记录请求 ID、判定标签、最终模型、判定来源、置信度、耗时和创建时间。判定来源包括样本匹配和规则判断，并可跳转到对应调用日志。
![智能路由决策](../../img/ai/ai_gateway_smart_routing_sample_juece.png)
{: .browser-mockup}
!!! info "统计信息"
    展示简单/复杂请求占比、样本匹配占比、总 Token、平均 Token、失败请求，以及按标签、来源、模型和 Token 的分布。
![智能路由统计](../../img/ai/ai_gateway_smart_routing_sample_tongji.png)
{: .browser-mockup}
## 7 内容合规

!!! note ""
    内容合规支持敏感词匹配和基于 Embedding 的语义审核样本。启用前，需要先在 **设置 -> 内容合规** 中打开总开关；使用审核样本时，还需要完成 **设置 -> Embedding** 配置。

!!! info "敏感词"
    支持创建和批量导入敏感词，并设置敏感词分组、归一化词、状态和备注。归一化词用于将不同写法统一为同一个匹配词。

![AI 网关内容合规](../../img/ai/ai_gateway_compliance.jpg)
{: .browser-mockup}

!!! info "敏感词分组"
    为一组敏感词设置处理动作、风险等级、状态和描述。处理动作包括 **阻断** 和 **仅记录**。
![AI 网关内容合规](../../img/ai/ai_gateway_compliance_fenzu.png)
{: .browser-mockup}
!!! info "审核样本"
    维护用于语义匹配的审核文本，并设置标签。列表展示向量模型和维度，样本变更或 Embedding 配置调整后可以重建向量。
![AI 网关内容合规](../../img/ai/ai_gateway_compliance_shenheyangben.png)
{: .browser-mockup}
!!! info "审计日志"
    记录 Request ID、请求模型、命中词、命中分组、处理动作、状态码和创建时间，用于追踪被记录或阻断的请求。

## 8 用量统计

!!! note ""
    **用量统计** 提供概览、分布、排行榜和调用日志 4 个视图，并支持按用户、模型供应商、模型和关键字筛选。
!!! info "概览"
    展示请求数、总 Token、输入 Token、输出 Token、缓存 Token、缓存命中率、活跃用户、活跃模型、失败请求、平均 Token/请求和使用趋势。
![AI 网关用量统计](../../img/ai/ai_gateway_usage_new.jpg)
{: .browser-mockup}

!!! info "分布"
    按模型供应商、模型、模型账号、用户组和用户统计请求数、Token 用量、缓存 Token 和占比。

![AI 网关用量分布](../../img/ai/ai_gateway_usage_new_fenbu.png)
{: .browser-mockup}

!!! info "排行榜"
    按用户展示请求数、输入 Token、输出 Token、Token 总量和缓存 Token，并支持按指标排序。

![AI 网关用量排行榜](../../img/ai/ai_gateway_usage_new_paihangbang.png)
{: .browser-mockup}

!!! info "调用日志"
    展示 Request ID、模型供应商、请求模型、上游模型、用户、用户组、输入/输出/总 Token、缓存 Token、状态码、响应时间和请求时间。点击 **详情** 可以查看单次调用信息。
![AI 网关用量调用日志](../../img/ai/ai_gateway_usage_new_diaoyongrizhi.png)
{: .browser-mockup}
## 9 网关设置

### 9.1 基础设置

!!! note ""
    **基础设置** 用于控制网关开关、监听端口、外部连接地址和负载策略。外部连接地址应填写客户端实际可访问的地址，并包含 `/v1` 路径。

![AI 网关基础设置](../../img/ai/ai_gateway_settings_basic.jpg)
{: .browser-mockup}

### 9.2 性能设置

!!! info "参数说明"
    - **最大并发**：同时处理的最大请求数
    - **等待队列大小**：超过并发限制后允许排队的请求数
    - **队列等待超时**：请求在队列中的最长等待时间
    - **非流式请求超时**：普通请求的最长执行时间
    - **流式空闲超时**：流式响应无数据返回时的最长等待时间
    - **最大请求体**：单次请求体大小限制
    - **Runtime 刷新间隔**：运行时配置刷新间隔

![AI 网关性能设置](../../img/ai/ai_gateway_settings_performance.jpg)
{: .browser-mockup}

### 9.3 Embedding 设置

!!! note ""
    Embedding 服务同时用于智能路由样本和内容合规审核样本的语义匹配。页面支持配置服务地址、模型、API Key，并提供连接测试。

#### 9.3.1 部署 Embedding 模型

1. 进入 **AI -> 模型 -> 下载器**，下载 `Qwen3-Embedding-0.6B-GGUF` 模型，并确认模型文件中包含 `qwen3-embedding-0.6b-q8_0.gguf`。

![下载 Qwen3 Embedding 模型](../../img/ai/ai_gateway_embedding_model_download.jpg)
{: .browser-mockup}

2. 进入 **应用商店**，搜索并安装 `llama.cpp`。
3. 在安装参数中，将 **模型目录** 设置为：

    ```text
    /opt/1panel/ai/models
    ```

4. 将 **启动参数** 设置为：

    ```text
    -m /models/Qwen3-Embedding-0.6B-GGUF/qwen3-embedding-0.6b-q8_0.gguf --host 0.0.0.0 --port 8080 --embedding --pooling last -c 32768
    ```

![llama.cpp Embedding 参数配置](../../img/ai/ai_gateway_embedding_llama_cpp.jpg)
{: .browser-mockup}

5. 完成安装，并确认 `llama.cpp` 应用处于运行状态。

> **模型目录** 是宿主机上的 `/opt/1panel/ai/models`，该目录在 `llama.cpp` 容器内挂载为 `/models`，因此启动参数中的模型路径需要以 `/models` 开头。

#### 9.3.2 连接 AI 网关

进入 **AI -> AI 网关 -> 设置 -> Embedding**，填写以下参数：

!!! info "连接参数"
    - **地址**：`http://127.0.0.1:8080`
    - **模型**：`Qwen3-Embedding-0.6B`
    - **API Key**：本地 `llama.cpp` 未配置认证时留空

![AI 网关 Embedding 设置](../../img/ai/ai_gateway_embedding_settings.jpg)
{: .browser-mockup}

点击 **连接测试**。测试成功后保存配置，再到智能路由样本或内容审核样本页面生成或重建向量。

!!! info "判定参数"
    - **路由阈值**：请求与智能路由样本的相似度达到该值后，才采用样本匹配结果
    - **审核阈值**：请求与内容审核样本的相似度达到该值后，才认为命中审核样本
    - **TopK**：每次参与判定的最相似样本数量

> 修改 Embedding 地址、模型或判定参数后，应回到智能路由样本和内容审核样本页面重建向量。

### 9.4 智能路由与内容合规设置

!!! note ""
    在 **智能路由** 标签页中打开开关，并选择简单模型组和复杂模型组。简单模型组适合低成本任务，复杂模型组适合代码分析、架构设计和故障排查等任务。

![AI 网关智能路由设置](../../img/ai/ai_gateway_settings_smart_routing.jpg)
{: .browser-mockup}

在 **内容合规** 标签页中可以统一启用或停用内容合规检查。

### 9.5 日志设置

!!! info "参数说明"
    - **AI 网关日志保留天数**：控制本地网关日志的保留周期
    - **日志清理间隔**：控制后台日志清理任务的执行间隔
    - **清空日志**：立即清理已有 AI 网关日志，请谨慎操作

### 9.6 Elasticsearch 设置

!!! note ""
    Elasticsearch 用于保存 AI 网关请求和响应内容，便于检索、审计和问题排查。页面支持连接测试，确认连接可用后再保存配置。

![AI 网关 Elasticsearch 设置](../../img/ai/ai_gateway_settings_elasticsearch.jpg)
{: .browser-mockup}

!!! info "参数说明"
    - **启用**：控制是否向 Elasticsearch 写入请求和响应内容
    - **地址**：Elasticsearch 服务地址，例如 `http://127.0.0.1:9200`
    - **认证方式**：选择 Elasticsearch 使用的认证方式
    - **用户名 / 密码**：使用 Basic Auth 时填写
    - **索引前缀**：写入数据使用的索引前缀
    - **单请求体最大保存大小**：限制单次写入的请求体大小，超过限制时会截断

> 请求和响应内容可能包含提示词、用户输入或业务上下文。请根据合规要求限制 Elasticsearch 的网络访问范围、账号权限和数据保留周期。
