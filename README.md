# docs.rs MCP

An MCP server that enables searching for Rust crates and their documentation from docs.rs.

English | [日本語](./README_JA.md) | [Tiếng Việt](./README_VI.md)

## Overview

docs.rs MCP is an MCP server that searches the Rust crate documentation site [docs.rs](https://docs.rs). By using this, AI Agents can search for required crates and obtain the latest documentation as needed.

![](./docs/images/img-chat.png)

## Features

- Tools specialized for searching docs.rs
- Supports multiple use cases, from searching for crates themselves to searching for specific APIs
- LLM-friendly Markdown output

## Requirements

- Node.js 18 or newer
- VS Code, Cursor, Claude Desktop or any other MCP client

## Setup

### Visual Studio Code (VSCode)

Add the following to `.vscode/mcp.json`:

```json
{
  "servers": {
    "docs-rs": {
      "command": "npx",
      "args": ["-y", "github:GSCFin/docs-rs-mcp"]
    }
  }
}
```

### Claude Code

Run the following command:

```text
claude mcp add docs-rs -s project -- npx -y github:GSCFin/docs-rs-mcp
```

### Cursor

You can install by pressing the button below:

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=docs-rs&config=JTdCJTIyY29tbWFuZCUyMiUzQSUyMCUyMm5weCUyMiUyQyUyMCUyMmFyZ3MlMjIlM0ElMjAlNUIlMjIteSUyMiUyQyUyMCUyMmdpdGh1YiUzQUdTQ0ZpbiUyRmRvY3MtcnMtbWNwJTIyJTVEJTdE)

Or, add a new MCP server that runs the `npx -y github:GSCFin/docs-rs-mcp` command from `Cursor Settings > MCP > Add new MCP Server`.

### Kilocode

Add to MCP settings in `Settings > MCP Servers`:

```json
{
  "mcpServers": {
    "docs-rs": {
      "command": "npx",
      "args": ["-y", "github:GSCFin/docs-rs-mcp"]
    }
  }
}
```

### Antigravity

Add to your MCP configuration:

```json
{
  "mcpServers": {
    "docs-rs": {
      "command": "npx",
      "args": ["-y", "@nuskey8/docs-rs-mcp@latest"]
    }
  }
}
```

### Gemini CLI

Add to `~/.gemini/settings.json`:

```json
{
  "mcpServers": {
    "docs-rs": {
      "command": "npx",
      "args": ["-y", "@nuskey8/docs-rs-mcp@latest"]
    }
  }
}
```

### Others

For other tools, please refer to the documentation as needed and add an MCP server that runs the `npx -y github:GSCFin/docs-rs-mcp` command.

## Tools

| Tool                      | Description                                                                                           |
| ------------------------- | ----------------------------------------------------------------------------------------------------- |
| `docs_rs_search_crates`   | Searches for crates by keyword.                                                                       |
| `docs_rs_readme`          | Retrieves the README/overview of the specified crate.                                                 |
| `docs_rs_get_item`        | Retrieves documentation for a specific item (module, struct, trait, enum, function, etc.) in a crate. |
| `docs_rs_search_in_crate` | Searches for traits, structs, methods, etc. from the all.html page in a crate.                        |

## License

This library is provided under the [MIT License](./LICENSE).
