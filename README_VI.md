# docs.rs MCP

Máy chủ MCP cho phép tìm kiếm các crate Rust và tài liệu của chúng từ docs.rs.

English | [日本語](./README_JA.md) | [Tiếng Việt](./README_VI.md)

## Tổng Quan

docs.rs MCP là một máy chủ MCP dùng để tìm kiếm trang tài liệu crate Rust [docs.rs](https://docs.rs). Bằng cách sử dụng công cụ này, AI Agent có thể tìm kiếm các crate cần thiết và lấy tài liệu mới nhất khi cần.

![](./docs/images/img-chat.png)

## Tính Năng

- Công cụ chuyên biệt để tìm kiếm docs.rs
- Hỗ trợ nhiều trường hợp sử dụng, từ tìm kiếm các crate đến tìm kiếm các API cụ thể
- Đầu ra Markdown thân thiện với LLM

## Yêu Cầu

- Node.js 18 trở lên
- VS Code, Cursor, Claude Desktop hoặc bất kỳ MCP client nào khác

## Cài Đặt

### Visual Studio Code (VSCode)

Thêm nội dung sau vào `.vscode/mcp.json`:

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

Chạy lệnh sau:

```text
claude mcp add docs-rs -s project -- npx -y github:GSCFin/docs-rs-mcp
```

### Cursor

Bạn có thể cài đặt bằng cách nhấn nút bên dưới:

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=docs-rs&config=JTdCJTIyY29tbWFuZCUyMiUzQSUyMCUyMm5weCUyMiUyQyUyMCUyMmFyZ3MlMjIlM0ElMjAlNUIlMjIteSUyMiUyQyUyMCUyMmdpdGh1YiUzQUdTQ0ZpbiUyRmRvY3MtcnMtbWNwJTIyJTVEJTdE)

Hoặc, thêm một MCP server mới chạy lệnh `npx -y github:GSCFin/docs-rs-mcp` từ `Cursor Settings > MCP > Add new MCP Server`.

### Kilocode

Thêm vào cài đặt MCP trong `Settings > MCP Servers`:

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

Thêm vào cấu hình MCP của bạn:

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

Thêm vào `~/.gemini/settings.json`:

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

### Khác

Đối với các công cụ khác, vui lòng tham khảo tài liệu khi cần và thêm một MCP server chạy lệnh `npx -y github:GSCFin/docs-rs-mcp`.

## Công Cụ

| Công Cụ                   | Mô Tả                                                                                           |
| ------------------------- | ----------------------------------------------------------------------------------------------- |
| `docs_rs_search_crates`   | Tìm kiếm các crate theo từ khóa.                                                                |
| `docs_rs_readme`          | Lấy README/tổng quan của crate được chỉ định.                                                   |
| `docs_rs_get_item`        | Lấy tài liệu cho một item cụ thể (module, struct, trait, enum, function, v.v.) trong một crate. |
| `docs_rs_search_in_crate` | Tìm kiếm traits, structs, methods, v.v. từ trang all.html trong một crate.                      |

## Giấy Phép

Thư viện này được cung cấp theo [Giấy phép MIT](./LICENSE).
