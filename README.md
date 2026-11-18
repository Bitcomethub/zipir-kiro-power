# Zıpır power for Kiro

Turns a document into a video lesson with a source citation on every scene. Zıpır reads a PDF, Word file, PowerPoint deck, Markdown, plain text or a web page, builds a storyboard you approve, and renders a Turkish-narrated, subtitled video in which every on-screen sentence is quoted from your own source with its page and line.

The power bundles the hosted Zıpır MCP server (`https://api.zipirapp.com/mcp`, streamable HTTP) and one skill that walks the flow: read usage, list formats, create a lesson, review the storyboard, approve, download.

## Setup

1. In Kiro open **Powers → Add Custom Power → Import power from GitHub** and paste `https://github.com/Bitcomethub/zipir-kiro-power`.
2. The first tool call opens the Zıpır consent screen in your browser. Sign in with a Zıpır account (Google, GitHub or an e-mail link). The power stores no credentials; Kiro keeps the OAuth token.
3. Mention "video lesson", "training video" or "document" and the power activates.

## What it does

- Tools: `list_formats`, `list_voices`, `list_lessons`, `create_lesson`, `get_lesson`, `edit_lesson`, `approve_lesson`, `rerender`, `get_download`, `get_usage`, `delete_lesson`
- Nothing renders until you approve the storyboard; `approve_lesson` is the only call that starts a render and uses the account's video minutes.
- The account and plan live on https://zipirapp.com. This power never takes a payment and sells nothing.

## Support and privacy

- Support: merhaba@zipirapp.com · Help: https://zipirapp.com/yardim/
- Privacy policy: https://zipirapp.com/gizlilik/ · Terms: https://zipirapp.com/sartlar/
- API documentation: https://zipirapp.com/en/api/

## License

MIT for this power package. Zıpır itself is a hosted service by VitrinAI Digital Studio.
