# 使用 1Panel 可视化安装 Ollama

!!! note ""
     **Ollama** 是一个开源的大型语言模型服务，提供了类似 OpenAI 的 API 接口和聊天界面，可以非常方便地部署最新版本的 GPT 模型并通过接口使用。支持热加载模型文件，无需重新启动即可切换不同的模型。

## 1. 打开应用商店

!!! note ""
    进入 1Panel 控制台后，点击左侧菜单的 **「应用商店」**。

![image-20251016110510084](../../img/app/appstores.png)

## 2. 搜索 Ollama 并安装

!!! note ""
    在右上角搜索框输入 **Ollama**，点击应用卡片进入详情页，选择 **安装**。

![image-20251017163039229](../../img/app/ollama.png)

## 3. 配置安装参数

!!! note ""
     你可以根据需要配置

    - **名称** (输入框内可自定义应用名称，默认为 ollama)
    - **版本** (下拉选择所需的 Ollama 版本)
    - **端口** (应用的访问端口，默认为 11434)
    - **端口外部访问** (开启后，将允许从外部网络访问此应用端口)
    
    确认设置无误后，点击 **确认** 按钮开始安装。


![image-20251017163107970](../../img/app/ollama_install.png)

!!! note ""
     等待安装完成即可

## 4. 访问 Ollama 服务

!!! note ""
     配置默认访问地址，已配置则忽略此步骤

![image-20251016172322315](../../img/app/setting_ip.png)

!!! note ""
     返回应用商店，点击 **跳转** 即可访问 Ollama 服务

![image-20251017171351530](../../img/app/ollama_jump.png)

!!! note ""
     访问页面，可以看到 `Ollama is running` 表示搭建成功

![image-20251017171445095](../../img/app/ollama_view.png)

!!! note ""
     点击 **终端** 连接ollama，使用命令控制

![image-20251017171937567](../../img/app/ollama_use.png)