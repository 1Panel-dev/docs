# 1Panel MCP Server

1Panel MCP 服务器是一个用于 1Panel 的模型上下文协议（Model Context Protocol，MCP）服务器实现。

## 安装

### 前提条件

- Go 1.23.0 或更高版本 
- 已有 1Panel

### 从源代码构建

1. 克隆仓库：

```bash
git clone https://github.com/1Panel-dev/mcp-1panel.git
cd mcp-1panel
```

2. 构建项目：

```bash
make build
```

> 将 ./build/mcp-1panel 移动至系统环境变量

### 使用 go install 安装

```bash
go install github.com/1Panel-dev/mcp-1panel@latest
```

## 使用方法

**Cursor**、**Windsurf** 配置示例:

```json
{
  "mcpServers": {
    "mcp-1panel": {
      "command": "mcp-1panel",
      "env": {
        "PANEL_ACCESS_TOKEN": "<your 1Panel access token>",
        "PANEL_HOST": "such as http://localhost:8080"
      }
    }
  }
}
```

> 还可以使用Claude、Windsurf、Cline等MCP客户端。

### 命令行选项

- `-token`：1Panel 访问令牌
- `-host`：1Panel 访问地址
- `-transport`：传输类型（stdio 或 sse，默认：stdio）
- `-sse-port`：启动 SSE 服务器端口（默认：8000）

### 环境变量

您也可以使用环境变量配置服务器：

- `PANEL_HOST`：1Panel 访问地址
- `PANEL_ACCESS_TOKEN`：1Panel 访问令牌

## 可用工具

服务器提供了各种与 1Panel 交互的工具：

| 工具                         | 类别 | 描述               |
|-----------------------------|------|------------------|
| **get_dashboard_info**      | 系统 | 列出概览页状态      |
| **get_system_info**         | 系统 | 获取系统信息        |
| **list_websites**           | 网站 | 列出所有网站        |
| **create_website**          | 网站 | 创建网站           |
| **list_ssls**               | 证书 | 列出所有证书        |
| **create_ssl**              | 证书 | 创建证书           |
| **list_installed_apps**     | 应用 | 列出所有已安装应用   |
| **install_openresty**       | 应用 | 安装 OpenResty     |
| **install_mysql**           | 应用 | 安装 MySQL         |
| **list_databases**          | 数据库 | 列出所有数据库     |
| **create_database**         | 数据库 | 创建数据库        |