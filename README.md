## Example MCP Server Configuration

To use this server with an MCP client that supports a `mcpServers` configuration, add the following entry:

```json
"mcpServers": {
	"Chess": {
		"command": "/Users/jmpurush/.local/bin/uv",
		"args": [
			"--directory",
			"/Users/jmpurush/mywork/ai-llm/mcp/mcp-build-chess",
			"run",
			"chess"
		]
	}
}
```

This will launch the MCP Chess server using the `uv` runner from the specified directory.
# mcp-build-chess

This project provides an MCP (Model Context Protocol) server for interacting with the Chess.com API. It exposes tools to get player profiles and stats via the MCP protocol.

## Requirements
- Python 3.13+
- [mcp](https://pypi.org/project/mcp/) (installed automatically via dependencies)

## Installation

Clone the repository and install dependencies:

```bash
pip install .
```

## Usage

You can run the MCP server using the standard MCP protocol (stdio transport):

```bash
python -m chess.server
```

Or, if installed as a package (after `pip install .`):

```bash
chess
```

This will start the server and listen for MCP requests via standard input/output.

## Tools Provided
- `get_chess_player_profile(username: str)`: Get the public profile for a Chess.com player by username.
- `get_chess_player_stats(username: str)`: Get the stats for a Chess.com player by username.

## Example

To test locally, you can run:

```bash
python -m chess.server
```

and send MCP requests to the process via stdio or using an MCP client.

---

For more details, see the code in `src/chess/server.py` and `src/chess/chess_api.py`.
