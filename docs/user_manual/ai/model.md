## 1 Managing Ollama Application

1.1 Installing Ollama from the App Store

!!! Abstract ""
    To use the model management feature, you need to first install the Ollama application from the App Store. After installation, you can view the status of the Ollama application on this page and perform operations such as starting, stopping, and restarting.

![img.png](../../img/ai/overview.png)

## 2 Adding Models

!!! Abstract ""
    Click "Add Model," enter the model name, and click the "Add" button to pull the corresponding model from the [Ollama Official Repository](https://ollama.com/search).

![img.png](../../img/ai/model_pull.png)

## 3 Running Models

!!! Abstract ""
    Click the "Run" button in the row of a specific model to open an online terminal on the current page and interact with the model.

![img.png](../../img/ai/model_run.png)

## 4 AI Proxy Enhancement

!!! Abstract ""
    This feature allows you to configure a reverse proxy for the Ollama application, supporting domain names, HTTPS, IP whitelists, and other configurations to enhance security when using large models.

![img.png](../../img/ai/api_proxy.png)

## 5 Viewing Connection Information

!!! Abstract ""
    Click the "Connection Information" button at the top of the list to view the connection information for the Ollama application.

![img.png](../../img/ai/connection_info.png)

> The Ollama application deployed from the App Store runs in a containerized manner. Different scenarios require selecting the corresponding connection information based on the prompts on the page.

## 6 Syncing from the Server

!!! Abstract ""
    When models are added using other tools or applications, and the model list information does not match the actual state, you can click the "Sync from Server" button at the top of the list to actively query the current model list from Ollama.

## 7 WEB Management Tools

!!! Abstract ""
    If you need to use a WEB graphical interface to manage and use Ollama, you can click the "OpenWebUI" button at the top of the list to navigate to the corresponding tool page.

    Currently supported management tools include:
    
    - [OpenWebUI](https://github.com/open-webui/open-webui)
