# Book a Sponsor plugin

Newsletter sponsor data for AI agents (Claude, ChatGPT, Cursor, Grok Build): which brands sponsor newsletters like yours, which brands sponsor newsletters by topic, and what newsletters charge for a sponsor slot.

This plugin connects your agent to the Book a Sponsor MCP server at `https://bookasponsor.com/mcp` (streamable HTTP, no sign-in) and adds a skill that tells the agent which tool to use.

## Tools
| Tool | What it does |
|---|---|
| `find_newsletter_sponsors` | Give it a newsletter's web address; it finds similar newsletters and the brands that sponsored them, with where and when each ad ran |
| `get_sponsor_scan` | Reads back a scan that was still running |
| `list_brands_sponsoring_newsletters` | Brands seen in the most newsletters in the last 12 months, overall or by topic |
| `get_newsletter_sponsorship_rates` | Median price newsletters list for the main sponsor slot, by list size |

Results name brands, never people or email addresses.

## Try it
- "Which brands might sponsor my newsletter, yourname.substack.com?"
- "What brands sponsor AI newsletters?"
- "What should I charge for a sponsor slot at 12,000 subscribers?"

## Install
- **Claude Code:** this repo is a plugin marketplace. Install the plugin (MCP server + skill) with:
  ```
  /plugin marketplace add rdoyle99/book-a-sponsor-plugin
  /plugin install book-a-sponsor@book-a-sponsor
  ```
- **Skill only (Claude Code, Cursor, Codex and other agents):** `npx skills add rdoyle99/book-a-sponsor-plugin`
- **Server only (Claude Code, Cursor, other hosts):**
  `claude mcp add --transport http book-a-sponsor https://bookasponsor.com/mcp`
- **Any MCP client:** `.mcp.json` is the Claude Code shape (`"type": "http"`); `mcp.json` is the Agent Plugins shape (`"type": "streamable-http"`). Both point at the same server.

Also listed in the official MCP registry as `com.bookasponsor/book-a-sponsor`.

Site: https://bookasponsor.com · Privacy: https://bookasponsor.com/privacy · Terms: https://bookasponsor.com/terms

License: MIT (this plugin). The data stays Book a Sponsor's.
