# 1Panel MCP Server

1Panel MCP Server is an implementation of the Model Context Protocol (MCP) server for 1Panel.

## Installation

### Prerequisites

- Go 1.23.0 or higher (for binary usage)
- Docker (for Docker usage)
- 1Panel installed

### Build from Source (Binary)

1. Clone the repository:

```bash
git clone https://github.com/1Panel-dev/mcp-1panel.git
cd mcp-1panel
```

2. Build the project:

```bash
make build
```

Move `./build/mcp-1panel` to a directory included in the system's `PATH` environment variable.

### Install via `go install`

```bash
go install github.com/1Panel-dev/mcp-1panel@latest
```

## Usage

You can use 1Panel MCP Server with tools like Cursor and Windsurf.

### stdio Mode

#### Binary Method

Ensure Go is installed and the binary is built or installed:

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

#### Docker Method

Ensure Docker is installed:

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

### SSE Mode

Start the MCP server with SSE:

```bash
mcp-1panel -host <your 1Panel access address> -token <your 1Panel access token> -transport sse -addr "http://localhost:8000"
```

Configuration example for Cursor/Windsurf:

```json
{
  "mcpServers": {
    "mcp-1panel": {
        "url": "http://localhost:8000/sse"
    }
  }
}
```

### Command-line Options

- `-token`: 1Panel access token
- `-host`: 1Panel access address
- `-transport`: Transport type (stdio or sse, default: stdio)
- `-sse-port`: Port for the SSE server (default: 8000)

### Environment Variables

You can also configure the server using environment variables:

- `PANEL_HOST`: 1Panel access address
- `PANEL_ACCESS_TOKEN`: 1Panel access token

## Available Tools

The server provides various tools for interacting with 1Panel:

| Tool                          | Category | Description                  |
|-------------------------------|----------|------------------------------|
| **get_dashboard_info**        | System   | List dashboard status        |
| **get_system_info**           | System   | Get system information       |
| **list_websites**             | Website  | List all websites            |
| **create_website**            | Website  | Create a website             |
| **list_ssls**                 | SSL      | List all SSL certificates    |
| **create_ssl**                | SSL      | Create an SSL certificate    |
| **list_installed_apps**       | App      | List all installed applications |
| **install_openresty**         | App      | Install OpenResty            |
| **install_mysql**             | App      | Install MySQL                |
| **list_databases**            | Database | List all databases           |
| **create_database**           | Database | Create a database            |

