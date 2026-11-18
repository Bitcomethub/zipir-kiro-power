---
name: zipir-document-to-video
description: Use when the user wants a document, PDF, deck, text or web page turned into a narrated video lesson whose on-screen sentences cite their source.
---

Zıpır builds a Turkish-narrated, subtitled video from a written source (PDF, Word, PowerPoint, Markdown, plain text or a web page). Every on-screen sentence is a quote from the source with its place in it. It is not an avatar, talking-head or camera tool.

## Flow

1. `get_usage` to read the account's usage and allowance before starting.
2. `list_formats` (and `list_voices` if the user names a voice) to read the real catalog. Never invent a format or voice id.
3. `create_lesson` with the document as a file, or with `text` or `url`. This does not start a render.
4. Poll `get_lesson`. When `needs_approval` is true the storyboard is ready: tell the user how many scenes and how long, and ask for approval.
5. Call `approve_lesson` only after the user explicitly agrees. This is the call that starts rendering.
6. Poll `get_lesson` until the status is `done`, then `get_download` for a signed link (valid 900 seconds).
7. `list_lessons` for "my videos"; `edit_lesson` to change one scene; `delete_lesson` only when the user asks.

## Rules

- Never call `approve_lesson` without an explicit user go-ahead.
- Do not add sentences that are not in the source; the video text is quoted from it.
- Report errors in plain words and say what the user can do next. Do not retry a failed render in a loop.
- Account and plan changes happen on https://zipirapp.com, not through this integration. It never takes a payment.

## Links

- API documentation: https://zipirapp.com/en/api/
- Support: merhaba@zipirapp.com
- Privacy: https://zipirapp.com/gizlilik/ · Terms: https://zipirapp.com/sartlar/
