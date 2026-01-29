# 使用 1Panel 可视化安装 Moltbot

!!! note ""
     **Moltbot**（原 Clawdbot） 是一款开源、自托管的个人 AI 助手，可以在本地计算机上运行，兼容 MacOS、Windows 及 Linux 等多种系统，支持接入常用聊天工具，除了内置多种 Agent 常用工具外，还可以通过插件和 Skill 扩展更多能力。

## 1. 打开应用商店

!!! note ""
    进入 1Panel 控制台后，点击左侧菜单的 **「应用商店」**。

![image-appstores](../../img/app/appstores.png)

## 2. 安装 Moltbot

!!! note ""
    点击首页 **Moltbot** 应用卡片进入详情页，选择 **安装**。

!!! note ""
     您可以根据需要配置：

    - **名称** (输入框内可自定义应用名称，默认为 moltbot)
    - **版本** (下拉选择所需的 Moltbot 版本)
    - **模型提供商** (下拉选择所需的 AI 模型提供商)
    - **API Key** (调用模型提供商接口使用的 API Key，在模型提供商处获取)
    - **模型** (模型提供商代号/模型ID)
    - **WebUI 端口** (默认为 18789)
    - **Bridge 端口** (默认为 18790)
    - **端口外部访问** (开启后，将允许从外部网络访问此应用端口)
    
    确认设置无误后，点击 **确认** 按钮开始安装。

!!! note "常见模型提供商与示例模型"
    
     - OpenAI: `openai/gpt-4o-mini`
     - Anthropic: `anthropic/claude-3-7-sonnet`
     - Gemini: `gemini/gemini-1.5-pro`
     - Groq: `groq/llama-3.1-70b-versatile`
     - Mistral: `mistral/large-latest`
     - Cohere: `cohere/command-r-plus`
     - MiniMax: `minimax/MiniMax-M2.1`
     - Moonshot (Kimi): `moonshot/kimi-k2.5`
     - Qwen: `qwen/qwen2.5-coder-32b-instruct`
     - ZAI (GLM): `zai/glm-4.7`
     - DeepSeek: `deepseek/deepseek-chat`

![image-moltbot_install](../../img/app/moltbot_install.png)

## 3. 获取 Moltbot Token

!!! note ""
     在 **已安装应用页面**，找到 **Moltbot** 应用点击 **文件夹图标** 进入应用数据目录，在目录下的 `data/conf` 文件夹，点击 **moltbot.json** 文件，复制其中 "gateway.auth.token" 的值，用作访问 Moltbot 应用时的 Token。

     ```json
     "gateway": {
     "mode": "local",
          "token": "c9917c5a066beeb26266d09baed99495e7563b33c771e89a"
     },
     ***
     ```

### 4. 访问 Moltbot WebUI

!!! note ""
     返回 **已安装应用页面**，找到 Moltbot 应用，点击 **跳转** 按钮，在新打开的浏览器地址栏中，在 URL 后添加 `?token=你的 Moltbot Token`。
     成功进入后，即可在 Chat 页面与 Moltbot 进行对话了。

![image-moltbot_visit](../../img/app/moltbot_visit.png)

### 5. 配置聊天工具对接（可选）

!!! note ""
     如果你希望通过 Telegram、WhatsApp、Discord、iMessage 等聊天工具与机器人进行对话，可以在 **已安装应用页面** 找到 **Moltbot 应用**，点击顶部的 **进入安装目录** 按钮。点击文件列表顶部的 **终端** 按钮，在终端中执行以下命令配置对应的聊天工具对接。

     ```bash
     docker compose -f docker-compose-cli.yml run --rm moltbot-cli channels add
     ```