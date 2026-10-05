# SeekMyWay Plugins

Official SeekMyWay plugins for AI agents. Ask about any company or product and your agent gets **official information — specifications, pricing, availability and documentation — each with a link to the source page**. Free to start, no key needed.

- Website & all install guides: **https://discovery.seekmyway.com/plugins**
- MCP endpoint (used by every plugin): `https://agent.seekmyway.com/plugmcp` — no key needed (free trial quota per IP)
- Use your own API key (your plan's quota): `https://agent.seekmyway.com/mcp` with `Authorization: Bearer <YOUR_API_KEY>` — get a free key at https://discovery.seekmyway.com
- Tools: `find_company`, `get_company_facts`, `get_company_resources`, `report_observation`

> ⚠️ **This is the only official repository**, and `agent.seekmyway.com` is the only official MCP endpoint. Plugins from forks or other domains are not ours.

## Install

Download the package for your platform from the [latest release](https://github.com/seekmyway/seekmyway-plugins/releases/latest) (or the official website), then run the commands below. Verify downloads with `SHA256SUMS.txt` (`shasum -a 256 -c SHA256SUMS.txt --ignore-missing`).

| Platform | Package |
|---|---|
| Claude Code | [seekmyway-claude.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-claude.tgz) |
| OpenAI Codex | [seekmyway-codex.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-codex.tgz) |
| GitHub Copilot CLI | [seekmyway-copilot.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-copilot.tgz) |
| Gemini CLI | [seekmyway-gemini.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-gemini.tgz) |
| Cursor | [seekmyway-cursor.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-cursor.tgz) |
| Windsurf / Devin Desktop | [seekmyway-windsurf.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-windsurf.tgz) |
| Zed | [seekmyway-zed.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-zed.tgz) |
| Cline (VS Code / CLI) | [seekmyway-cline.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-cline.tgz) |
| OpenClaw | [seekmyway-openclaw.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-openclaw.tgz) |
| Hermes | [seekmyway-hermes.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-hermes.tgz) |
| Dify | [seekmyway-dify.difypkg](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-dify.difypkg) |
| n8n | [seekmyway-n8n.tgz](https://github.com/seekmyway/seekmyway-plugins/releases/latest/download/seekmyway-n8n.tgz) |

**Claude Code**
```bash
mkdir -p ~/.seekmyway && tar xzf seekmyway-claude.tgz -C ~/.seekmyway
claude plugin marketplace add ~/.seekmyway/seekmyway
claude plugin install seekmyway@seekmyway
```

**OpenAI Codex**
```bash
mkdir -p ~/.seekmyway && tar xzf seekmyway-codex.tgz -C ~/.seekmyway
codex plugin marketplace add ~/.seekmyway/seekmyway-codex
codex plugin add seekmyway@seekmyway
```

**GitHub Copilot CLI**
```bash
mkdir -p ~/.seekmyway && tar xzf seekmyway-copilot.tgz -C ~/.seekmyway
copilot plugin marketplace add ~/.seekmyway/seekmyway-copilot
copilot plugin install seekmyway@seekmyway
```
(Keep `~/.seekmyway` — Claude Code, Codex and Copilot load the plugin from there.)

**Gemini CLI**
```bash
tar xzf seekmyway-gemini.tgz
gemini extensions install ./seekmyway --consent
```

**Cursor** — then run *Developer: Reload Window*
```bash
mkdir -p ~/.cursor/plugins/local
tar xzf seekmyway-cursor.tgz -C ~/.cursor/plugins/local
```

**Windsurf / Devin Desktop** and **Cline** — the script only edits your local MCP settings (keeps your other servers, backs up the old file, no network access; `--uninstall` removes SeekMyWay only). On Windows use `py`.
```bash
tar xzf seekmyway-windsurf.tgz && python3 seekmyway-windsurf/install.py
tar xzf seekmyway-cline.tgz && python3 seekmyway-cline/install.py
```

**Zed** — install the skill, then add a remote MCP server `https://agent.seekmyway.com/plugmcp?client=zed` in *Settings → AI → MCP Servers*
```bash
mkdir -p ~/.agents/skills && tar xzf seekmyway-zed.tgz -C ~/.agents/skills
```

**OpenClaw**
```bash
openclaw plugins install ./seekmyway-openclaw.tgz --force --accept-capabilities
openclaw gateway restart
```

**Hermes**
```bash
mkdir -p ~/.hermes/plugins
tar xzf seekmyway-hermes.tgz -C ~/.hermes/plugins
hermes plugins enable seekmyway
```

**Dify (self-hosted)** — *Plugins → Install plugin → Local package*, choose `seekmyway-dify.difypkg`. Until the plugin is listed on the Dify Marketplace, self-hosted Dify needs `FORCE_VERIFYING_SIGNATURE=false` in `docker/.env`. Dify Cloud: add an MCP server (HTTP) with `https://agent.seekmyway.com/plugmcp?client=dify`.

**n8n (self-hosted)** — then restart n8n
```bash
mkdir -p ~/.n8n/nodes && cd ~/.n8n/nodes
npm install /path/to/seekmyway-n8n.tgz
```

**ChatGPT, Claude.ai, Perplexity, Copilot Studio, Meta Muse, Grok Bot, Goose, Cherry Studio, LibreChat, Flowise** — no package needed; add a custom MCP connector with `https://agent.seekmyway.com/plugmcp?client=<platform>`. Step-by-step guides: https://discovery.seekmyway.com/plugins

---

## 中文说明

SeekMyWay 官方插件:让 AI 智能体查询公司和产品的**官方信息(规格、价格、供货、文档),每条都附官网出处**。免费试用,无需 key。

- 官网与全部平台的安装说明:**https://discovery.seekmyway.com/plugins**(中国大陆用户建议直接从官网下载)
- MCP 地址:`https://agent.seekmyway.com/plugmcp`(不需要 key,按 IP 计免费试用额度);使用自己的 key:`https://agent.seekmyway.com/mcp` 加请求头 `Authorization: Bearer <你的 key>`
- 安装:从 [最新 Release](https://github.com/seekmyway/seekmyway-plugins/releases/latest) 下载对应平台的包,按上面的命令安装;可用 `SHA256SUMS.txt` 校验文件。
- ⚠️ **这是唯一的官方仓库**,官方 MCP 地址只有 `agent.seekmyway.com`。

## Security
Please report security issues to info@seekmyway.com (see [SECURITY.md](SECURITY.md)). Never put your API key in files that may be committed or shared.

## License
[MIT](LICENSE)
