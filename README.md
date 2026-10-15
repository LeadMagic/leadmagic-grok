# LeadMagic for Grok

<img src="assets/logo.svg" width="64" height="64" alt="LeadMagic logo">

Official LeadMagic plugin for **Grok** and **Grok Build**. Connect your agent to LeadMagic's hosted MCP for B2B research: **search** people, companies, and jobs; **find** and **validate** work emails; look up **professional mobile** numbers.

Published by LeadMagic Corporation.

[LeadMagic](https://leadmagic.io) · [MCP setup](https://leadmagic.io/docs/mcp/setup) · [Pricing](https://leadmagic.io/pricing)

This is licensed contact and company intelligence — the same class of product as enterprise GTM data platforms. It is **not** a scraper. Hosted MCP is OAuth only (no API key in this plugin).

## Install

### grok.com (custom connector)

1. Open [grok.com/connectors](https://grok.com/connectors) and choose **Custom**.
2. Enter `https://mcp.leadmagic.io/mcp`.
3. Complete the browser OAuth sign-in with your LeadMagic account (Google or email — the same account as [app.leadmagic.io](https://app.leadmagic.io)). There is no API key to paste.

### Grok Build CLI

```bash
grok mcp add --transport http leadmagic https://mcp.leadmagic.io/mcp
```

### Cursor

Use the dedicated [LeadMagic Cursor plugin](https://github.com/LeadMagic/leadmagic-cursor-plugin), which bundles the same hosted MCP with Cursor rules, skills, agents, and commands.

## Sign in

Hosted MCP is `https://mcp.leadmagic.io/mcp`. Your client starts OAuth and opens the browser. Sign in with the LeadMagic workspace you already use. Do not add `X-API-Key` or other headers to any MCP config.

If the browser stops on LeadMagic sign-in, finish it, then return to your client. Reconnect from MCP settings if tools still return `401`.

Details: [LeadMagic MCP authentication](https://leadmagic.io/docs/mcp/authentication)

## Skills

| Skill | What it covers |
| --- | --- |
| `account-intelligence` | Company research, enrichment, and account briefs |
| `market-search` | People, company, and job search |
| `find-work-email` | Work email finding with waterfall logic |
| `validate-work-email` | Email validation and deliverability |
| `find-mobile` | Professional mobile number lookup |
| `prospect-list-qc` | List cleanup and quality review |

## Testing

**Locally:** point any MCP client (Cursor, Grok Build CLI, or `npx @modelcontextprotocol/inspector`) at `https://mcp.leadmagic.io/mcp` and complete the OAuth flow. Run a people or company search and confirm results return.

**In-app:** connect the MCP in [grok.com/connectors](https://grok.com/connectors) or Cursor, then ask: *"Use LeadMagic to find the work email for a decision-maker at gong.io"* or *"Search LeadMagic for account executives at Series B SaaS companies in Austin."*

## xAI plugin catalog

The plugin follows the layout the [xai-org/plugin-marketplace](https://github.com/xai-org/plugin-marketplace) indexer reads: `.grok-plugin/plugin.json` for the manifest, `.mcp.json` for the hosted MCP server, and `skills/`. The catalog entry itself lives only in xai-org's `.grok-plugin/marketplace.json`; [`docs/xai-catalog-entry.example.json`](docs/xai-catalog-entry.example.json) is the entry to append there, with `sha` set to the 40-character SHA of the `leadmagic-grok` commit being submitted.

## License

MIT — see [LICENSE](LICENSE).

Support: [LeadMagic Support](https://leadmagic.io/docs/v1/support) · [Privacy](https://leadmagic.io/legal/privacy) · [Terms](https://leadmagic.io/legal/terms)
