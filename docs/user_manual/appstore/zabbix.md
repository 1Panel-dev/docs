# 使用 1Panel 可视化安装 Zabbix

!!! note ""
    **Zabbix** 是一款企业级开源分布式监控解决方案，可用于监控网络设备、服务器、服务及其他 IT 资源的性能和可用性。

## 1. 安装 Zabbix Server

### 1.1 打开应用商店

!!! note ""
    登录 1Panel 控制台后，点击左侧菜单的 **「应用商店」**。

<div class="browser-mockup" markdown>

![image-20251016110510084](../../img/app/appstores.png)

</div>

### 1.2 搜索并安装

!!! note ""
    在右上角搜索框输入 **Zabbix**，点击 **Zabbix Server** 应用卡片进入详情页，选择 **安装**。

<div class="browser-mockup" markdown>

![image-20251021163433091](../../img/app/zabbix.png)

</div>

### 1.3 配置安装参数

!!! note ""
    根据实际需求配置以下参数：

    - **名称**：可自定义应用名称（默认为 `zabbix-server`）
    - **版本**：选择需要安装的 Zabbix 版本
    - **HTTP 端口**：访问 Zabbix 的端口（默认为 8080）
    - **数据接收端口**：用于接收监控数据（默认为 10051）
    - **数据库服务**：选择存储数据的数据库服务（支持 MySQL）
    - **字符集**：数据库字符集（默认为 utf8mb4）
    - **排序规则**：建议选择 **utf8mb4_bin** 这种区分大小写的排序规则
    - **Root 密码**：默认为 MySQL 应用安装时设置的 Root 密码
    - **数据库**：为 Zabbix 创建的数据库名称
    - **数据库用户**：用于连接数据库的用户名
    - **数据库密码**：数据库用户的密码

    配置完成后，点击 **确认** 开始安装。

<div class="browser-mockup" markdown>

![image-20251021163633965](../../img/app/zabbix-server_install.png)

</div>

### 1.4 访问 Zabbix Server 服务

!!! note ""
    - 进入应用商店「已安装」页面，点击 **跳转** 即可访问 Zabbix Server
    - 默认登录账户：
        - 用户名：`Admin`
        - 密码：`zabbix`

<div class="browser-mockup" markdown>

![image-20251021163916064](../../img/app/zabbix-server_jump.png)

</div>

!!! note ""
    首次进入系统，可以根据以下步骤切换为中文界面：

    进入 **Administration** > **General** > **GUI**，在 **Default language** 中选择 **Chinese (zh_CN)**，然后点击 **Update** 保存。

<div class="browser-mockup" markdown>

![image-20251021163916064](../../img/app/zabbix-language.png)

</div>

### 1.5 添加监控主机

!!! note ""
    - 在 Zabbix Server 页面，点击 **数据采集** > **主机**  
    - 列表中默认的 **Zabbix Server** 主机可视情况删除  
    - 右上角点击 **创建主机**，填写主机信息：
        - **主机名称**：安装 Agent 时的 **监控主机名称** 要与这里保持一致
        - **模版**：选择 **Templates Operating systems** > **Linux by Zabbix agent**
        - **主机群组**：建议选择 **Linux servers**、**Zabbix servers**
        - **接口**：选择 **Agent**，添加正确的 **IP 地址** 和 **端口**

    配置完成后点击 **添加** 保存。

<div class="browser-mockup" markdown>

![image-20251021163916064](../../img/app/zabbix-hosts-add.png)

</div>

## 2. 安装 Zabbix Agent

### 2.1 搜索并安装

!!! note ""
    回到应用商店列表，在右上角输入 **Zabbix**，点击 **Zabbix Agent** 应用卡片进入详情页，选择 **安装**。

<div class="browser-mockup" markdown>

![image-20251021163433091](../../img/app/zabbix.png)

</div>

### 2.2 配置安装参数

!!! note ""
    根据实际需求配置以下参数：

    - **名称**：可自定义应用名称（默认为 `zabbix-agent`）
    - **版本**：选择需要安装的 Agent 版本
    - **Agent 端口**：Agent 上报数据使用的端口（默认为 10050）
    - **监控主机名称**：需与服务端配置的主机名称一致
    - **服务端地址**：Zabbix Server 的地址
    - **服务端端口**：Zabbix Server 的端口（默认为 10051）

    配置完成后，点击 **确认** 开始安装。

<div class="browser-mockup" markdown>

![image-20251021163633965](../../img/app/zabbix-agent_install.png)

</div>

### 2.3 查看 Agent 主机状态

!!! note ""
    进入 **数据采集** > **主机** 页面，查看 Agent 主机状态，若 **可用性** 列为绿色，表示 Agent 已成功连接到 Server。

<div class="browser-mockup" markdown>

![image-20251021163916064](../../img/app/zabbix-agent-status.png)

</div>
