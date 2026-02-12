# NWS MCP Server

This is my first MCP server created using documentation from <https://modelcontextprotocol.io/docs/>

To run this MCP server, you must install uv and initialize a venv

```curl -LsSf https://astral.sh/uv/install.sh | sh```

In the weather directory:
```uv sync```

Now: to integrate your desktop LLM (this uses Claude Desktop):
For other LLMs, reference the appropriate docs.
[For ChatGPT](https://developers.openai.com/api/docs/mcp/)

```<your_text_editor> ~/Library/Application\ Support/Claude/claude_desktop_config.json```

If you use windows:
```<your_text_editor> $env:AppData\Claude\claude_desktop_config.json```

Paste the following and write to file (make sure to change the filepath to your weather directory):
```
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/ABSOLUTE/PATH/TO/PARENT/FOLDER/weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

Now just use your LLM desktop app as normal and prompt it to use your MCP server.
If it is not working make sure that the MCP server is enabled in your app settings.
