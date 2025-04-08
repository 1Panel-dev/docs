# 1Panel MCP Server

1Panel MCP 服务器是一个用于 1Panel 的模型上下文协议（Model Context Protocol，MCP）服务器实现。

## 安装

### 前提条件

- Go 1.23.0 或更高版本 (二进制使用方式)
- Docker (Docker 使用方式)
- 已安装 1Panel

### 从源代码构建 (二进制)

1. 克隆代码仓库：

```bash
git clone https://github.com/1Panel-dev/mcp-1panel.git
cd mcp-1panel
```

2. 构建项目：

```bash
make build
```

将 `./build/mcp-1panel` 移动到系统环境变量 PATH 所包含的目录中。

### 使用 `go install` 安装

```bash
go install github.com/1Panel-dev/mcp-1panel@latest
```

## 使用方式

你可以将 1Panel MCP Server 与 Cursor 和 Windsurf 等工具配合使用。

### stdio 模式

#### 二进制方式

确保已安装 Go 并已构建或安装该二进制文件：

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

#### Docker 方式

确保已安装 Docker：

```json
{
  "mcpServers": {
    "mcp-1panel": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "-e",
        "PANEL_HOST",
        "-e",
        "PANEL_ACCESS_TOKEN",
        "1panel/1panel-mcp-server"
      ],
      "env": {
        "PANEL_HOST": "such as http://localhost:8080",
        "PANEL_ACCESS_TOKEN": "<your 1Panel access token>"
      }
    }
  }
}
```

### SSE 模式

使用 SSE 启动 MCP server：

```bash
mcp-1panel -host <your 1Panel access address> -token <your 1Panel access token> -transport sse -addr "http://localhost:8000"
```

Cursor/Windsurf 配置示例：

```json
{
  "mcpServers": {
    "mcp-1panel": {
        "url": "http://localhost:8000/sse"
    }
  }
}
```

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

| 工具                          | 类别 | 描述               |
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
