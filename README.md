# NWS MCP Server

This is my first MCP server created using documentation from <https://modelcontextprotocol.io/docs/>

To run this MCP server, you must install uv and initialize a venv

$ curl -LsSf https://astral.sh/uv/install.sh | sh

In the weather directory:
```
uv sync
source .venv/bin/activate
```

Now in claude:
```<your_text_editor> ~/Library/Application\ Support/Claude/claude_desktop_config.json```
If you use windows:
```<your_text_editor> $env:AppData\Claude\claude_desktop_config.json```
Paste the following and write to file:
```{
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

Now ```uv run weather.py```
