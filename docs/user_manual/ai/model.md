## Ollama

### 1 管理 Ollama 应用

!!! note ""
    要使用模型管理功能，需要先在应用商店中安装 Ollama 应用。Ollama 安装完成后可以在该页面查看 Ollama 应用状态，并进行启动、停止及重启等操作。

![img.png](../../img/ai/overview.png)
{: .original}

### 2 添加模型

!!! note ""
    点击添加模型，输入模型名称点击添加按钮即可从 [Ollama 官方仓库](https://ollama.com/search)拉取对应模型。

![img.png](../../img/ai/model_pull.png)
{: .original}

### 3 运行模型

!!! note ""
    点击某个模型所在行的【运行】操作，即可在当前页面打开在线终端与该模型进行对话。

![img.png](../../img/ai/model_run.png)
{: .original}

### 4 AI 代理增强

!!! note ""
    通过该功能可以为 Ollama 应用配置反向代理，从而支持域名、HTTPS、IP 白名单等配置，增强使用大模型时的安全性。

![img.png](../../img/ai/api_proxy.png)
{: .original}

### 5 查看连接信息

!!! note ""
    点击列表上方的【连接信息】按钮，即可查看 Ollama 应用的连接信息。

![img.png](../../img/ai/connection_info.png)
{: .original}

> 应用商店部署的 Ollama 采用容器化方式运行，不同的场景需要根据页面提示选择对应的连接信息。

### 6 从服务器同步

!!! note ""
    当使用了其他工具或应用程序添加了模型，模型列表信息与实际不一致时，可以点击列表上方的【从服务器同步】按钮，主动从 Ollama 查询当前模型列表。

### 7 WEB 管理工具

!!! note ""
    如果需要使用 WEB 图形化界面管理并使用 Ollama 时，可以列表上方的【OpenWebUI】按钮，跳转到对应工具页面。

    目前支持的管理工具有：
    
    - [OpenWebUI](https://github.com/open-webui/open-webui)

## TensorRT LLM

!!! note ""
    TensorRT LLM 是 NVIDIA 推出的全面开源库，用于在 NVIDIA GPU 上加速和优化最新大语言模型（LLM）的推理性能。

### 0 前置条件

!!! note ""
    在使用 TensorRT LLM 创建模型之前，需要先安装 NVIDIA 显卡驱动并安装配置 NVIDIA Container Toolkit。参考文档【[Installing the NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)】。

### 1 创建模型

!!! note ""
    在 TensorRT LLM 模型管理页面，点击【创建】按钮，输入模型名称等参数后，点击【确认】按钮即可创建模型。

!!! info "参数说明"
    - **名称**：模型名称。
    - **容器名称**：TensorRT LLM 模型管理功能，会使用 TensorRT LLM 镜像启动一个容器来运行模型，容器名称需要唯一，默认使用模型名称。
    - **镜像**：TensorRT LLM 镜像，默认使用 NVIDIA 官方镜像。
    - **版本**：TensorRT LLM 镜像的镜像标签，对应不同的 TensorRT LLM 版本，可以查看 [NVIDIA TensorRT LLM 官方仓库](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/tensorrt-llm/containers/release/tags) 获取可用版本。
    - **模型目录**：选择服务器上的本地模型目录挂载到容器中，需要将模型文件夹提前放置在该目录中。
    - **启动命令**：启动容器时执行运行模型的命令，默认使用 NVIDIA 官方启动命令，可以自定义启动命令。需要注意启动命令中的模型路径，1Panel 会将上一个参数的本地模型目录映射到容器的 /models 目录。如果选择的模型目录为最终的模型路径，例如 /home/DeepSeek-V3，那么启动命令中 `trtllm-server` 后直接跟 `/models` 即可；如果选择的模型目录为模型文件夹的父目录，例如最终模型路径为 /home/DeepSeek-V3，选择的模型目录参数为 /home，则启动命令中 `trtllm-server` 后需要跟 `/models/DeepSeek-V3` 路径。
    - **端口**：配置 TensorRT LLM 容器的端口映射，可以将容器启动命令中的 8000 端口映射到服务器的 8000 端口，从而可以通过服务器 IP:8000 访问 TensorRT LLM 服务（需要勾选端口外部访问）。
    - **环境变量**：为 TensorRT LLM 容器配置环境变量。
    - **挂载**：为 TensorRT LLM 容器挂载额外的目录，可以挂载服务器上的本地目录到容器中，从而可以在容器中访问服务器上的本地目录。

![img.png](../../img/ai/create_trtllm.png)
{: .original}

### 2 查看模型日志

!!! note ""
    在 TensorRT LLM 模型管理页面，点击模型所在行的【查看日志】按钮，即可查看模型启动及运行日志。

### 3 其他模型操作

!!! note ""
    在 TensorRT LLM 模型管理页面，可以对模型进行停止、启动、重启、删除、编辑等操作。
