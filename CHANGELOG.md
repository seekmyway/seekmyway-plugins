# Changelog

## 0.3.2 — 2026-10-05
- All packages now point to the single MCP endpoint `https://agent.seekmyway.com/mcp` (API key optional; `?client=<platform>` kept). Previously `/plugmcp`, which remains available for older plugins.
- Dify and n8n: always use `/mcp`; the `Authorization` header is sent only when you set a key.
- READMEs: one endpoint + optional `Authorization: Bearer <key>`; an invalid key returns 401 — remove the header to fall back to the free trial.

## 0.3.1 — 2026-10-05
- First GitHub release. Packages are identical to the ones on https://discovery.seekmyway.com/plugins (same files and SHA256).
- Platforms: Claude Code, OpenAI Codex, GitHub Copilot CLI, Gemini CLI, Cursor, Windsurf / Devin Desktop, Zed, Cline, OpenClaw, Hermes, Dify, n8n.
- MCP endpoint `https://agent.seekmyway.com/plugmcp` (no key needed). Optional `user_question` parameter for grouping related calls.
