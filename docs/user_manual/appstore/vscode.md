# 使用 1Panel 可视化安装 VS Code

!!! note ""
     **code-server** 是一款强大的开源工具，它将 Visual Studio Code (VS Code)带入了基于Web的在线环境。它使您可以通过Web浏览器远程访问和使用VS Code的功能，而无需在本地安装VS Code应用程序。

## 1. 打开应用商店

!!! note ""
    进入 1Panel 控制台后，点击左侧菜单的 **「应用商店」**。

![image-20251016110510084](../../img/app/appstore_white.png)

## 2. 搜索 VS Code 并安装

!!! note ""
    在右上角搜索框输入 **VS Code**，点击应用卡片进入详情页，选择 **安装**。

![image-20251021170400655](../../img/app/vs-code.png)

## 3. 配置安装参数

!!! note ""
     你可以根据需要配置

    - **名称** (输入框内可自定义应用名称，默认为 code-server)
    - **版本** (下拉选择所需的 code-server 版本)
    - **端口** (应用的访问端口，默认为 40031)
    - **网页访问密码** (设置 code-server 的登录密码)
    - **Sudo 密码** (设置应用内 `sudo` 命令的密码)
    - **端口外部访问** (开启后，将允许从外部网络访问此应用端口)
    
    确认设置无误后，点击 **确认** 按钮开始安装。

![image-20251021170633477](../../img/app/vs-code_install.png)

!!! note ""
     等待安装完成即可

## 4. 访问 VS Code 服务

!!! note ""
     安装完成后，确认 1Panel 配置默认访问地址，已配置过可忽略

![image-20251016172322315](../../img/app/setting_ip.png)

!!! note ""
     返回应用商店，点击 **跳转** 即可访问 VS Code 服务

![image-20251021171102110](../../img/app/vs-code_jump.png)

!!! note ""
     输入安装时设置的访问密码即可

![image-20251021171828689](../../img/app/vs-code_view.png)