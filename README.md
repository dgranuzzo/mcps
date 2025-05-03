This example uses the filesystem MCP server, running locally via npx.

Run it

uv run python examples/mcp/filesystem_example/main.py

Under the hood:

The server is spun up in a subprocess, and exposes a bunch of tools like list_directory(), read_file(), etc.
We add the server instance to the Agent via mcp_agents.
Each time the agent runs, we call out to the MCP server to fetch the list of tools via server.list_tools().
If the LLM chooses to use an MCP tool, we call the MCP server to run the tool via server.run_tool().
