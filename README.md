# Ausca

Connect an agent client to [Ausca](https://ausca.com), a set of pay-per-call services for document OCR and analysis, media transcription, browser sessions and receive-only agent inboxes. This plugin packages the production MCP endpoint at `https://ausca.com/mcp`, one [service-selection skill](skills/ausca-service-selection/SKILL.md), and the current square mark. It does not include a wallet, payment signer, API key or local server.

The public MCP tools can discover and inspect current offers. Preparation returns the exact terms for a request; paid invocation uses x402 and needs a compatible client and an explicit payment decision. Result and receipt reads must follow the authoritative invocation state. A successful discovery or preparation call is not a paid result.

## Connect now

```json
{
  "mcpServers": {
    "ausca": {
      "type": "http",
      "url": "https://ausca.com/mcp"
    }
  }
}
```

For Claude Code, `claude mcp add --transport http ausca https://ausca.com/mcp` adds the same remote connection. The host manifests in `.claude-plugin/`, `.cursor-plugin/` and `.grok-plugin/` package it for marketplace review. Root `plugin.json` and the schema-valid Streamable HTTP `mcp.json` also support local Codex plugin installation. Reviewed ChatGPT/Codex directory submission still needs Ausca's public terms and support URLs; a public source repository does not itself mean a marketplace card is approved.

Read the [MCP guide](https://ausca.com/docs/mcp) and the [current service skills](https://ausca.com/skills/) for service limits, payment flow, lifecycle and artifact retention. [Privacy](https://ausca.com/privacy) and support at `hello@ausca.com` are available on the product site. The [source repository](https://github.com/auscahq/ausca) contains the underlying service contracts.

The files in this plugin have a [limited plugin-use license](LICENSE). That license covers installation and use of the plugin files; it does not change the license of Ausca's service or source code.
