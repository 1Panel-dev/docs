# Install Ollama Visually Using 1Panel

!!! note ""
    **Ollama** is an open-source large language model service that provides an OpenAI-like API interface and chat interface. It allows you to easily deploy the latest GPT models and use them via APIs. It supports hot-reloading model files, enabling you to switch between different models without restarting the service.

## 1. Open the App Store

!!! note ""
    After entering the 1Panel console, click **App Store** in the left menu.

![image-20251016110510084](../../img/app/appstores.png)
{: .browser-mockup}

## 2. Search for Ollama and Install

!!! note ""
    Enter **Ollama** in the search box in the upper right corner, click the application card to go to the details page, then select **Install**.

![image-20251017163039229](../../img/app/ollama.png)
{: .browser-mockup}

## 3. Configure Installation Parameters

!!! note ""
    You can configure the following as needed:

    - **Name**: Customize the application name (default: ollama)
    - **Version**: Select the desired Ollama version from the dropdown
    - **Port**: Access port for the application (default: 11434)
    - **Port External Access**: When enabled, allows external network access to the application port

    After confirming the settings are correct, click the **Confirm** button to start installation.

![image-2025-1017163107970](../../img/app/ollama_install.png)
{: .browser-mockup}

!!! note ""
    Wait for the installation to complete.

## 4. Access the Ollama Service

!!! note ""
    Configure the default access address. Skip this step if already configured.

![image-20251016172322315](../../img/app/setting_ip.png)
{: .browser-mockup}

!!! note ""
    Return to the App Store and click **Jump** to access the Ollama service.

![image-20251017171351530](../../img/app/ollama_jump.png)
{: .browser-mockup}

!!! note ""
    If you see `Ollama is running` on the page, the deployment is successful.

![image-20251017171445095](../../img/app/ollama_view.png)
{: .browser-mockup}

!!! note ""
    Click **Terminal** to connect to Ollama and control it using commands.

![image-20251017171937567](../../img/app/ollama_use.png)
{: .browser-mockup}
