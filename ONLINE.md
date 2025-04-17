# modelscope-mcp-server-config.json
```
{
  "mcpServers": {
    "postgres": {
      "timeout": 60,
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "mcp/postgres",
        "postgresql://host.docker.internal:5432/mydb"
      ],
      "transportType": "stdio"
    },
    "sqlite": {
      "disabled": false,
      "timeout": 60,
      "command": "uvx",
      "args": [
        "mcp-server-sqlite",
        "--db-path",
        "test.db"
      ],
      "transportType": "stdio"
    },
    "playwright": {
      "timeout": 60,
      "command": "npx",
      "args": [
        "@playwright/mcp@latest",
        "--headless"
      ],
      "transportType": "stdio"
    },
    "filesystem": {
      "timeout": 60,
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "--mount",
        "type=bind,src=/Desktop,dst=/projects/Desktop",
        "--mount",
        "type=bind,src=/dir,dst=/projects/other/allowed/dir,ro",
        "--mount",
        "type=bind,src=/file.txt,dst=/projects/path/to/file.txt",
        "mcp/filesystem",
        "/projects"
      ],
      "transportType": "stdio"
    },
    "github": {
      "timeout": 60,
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "-e",
        "GITHUB_PERSONAL_ACCESS_TOKEN",
        "mcp/github"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxx"
      },
      "transportType": "stdio"
    },
    "fetch": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-25d501f7-5b9a-4542.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    },
    "mcp-playwright": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-3bad8dcb-0511-4549.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    },
    "duckduckgo-mcp-server": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-b40810b1-c592-4dd9.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    },
    "hive-mcp-server": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-1b97e221-b1e7-44c4.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    },
    "fiscal-data-mcp": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-b5218b69-24bc-497f.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    },
    "kospi-kosdaq-stock-server": {
      "disabled": false,
      "timeout": 60,
      "url": "https://mcp-0b046887-fe94-4b79.api-inference.modelscope.cn/sse",
      "transportType": "sse"
    }
  }
}

```