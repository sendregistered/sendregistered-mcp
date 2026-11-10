# SendRegistered MCP

<img src="assets/logo.png" alt="SendRegistered" width="128" height="128">

Official [SendRegistered](https://sendregistered.com) MCP server: quote, send and track registered letters with proof of delivery from your AI assistant. You approve every letter before it is printed and handed to the post.

## Install

### Gemini CLI

```bash
gemini extensions install https://github.com/sendregistered/sendregistered-mcp
```

Restart Gemini CLI. On first use it asks you to sign in to SendRegistered (OAuth).

### Cursor

[Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=sendregistered&config=eyJ1cmwiOiJodHRwczovL3NlbmRyZWdpc3RlcmVkLmNvbS9tY3AifQ==) opens Cursor with the server filled in. You can also paste this snippet into `.cursor/mcp.json` in a project, or into `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "sendregistered": { "url": "https://sendregistered.com/mcp" }
  }
}
```

Cursor then asks you to sign in.

### Claude

1. In Claude, open Settings, then Connectors, and choose Add custom connector.
2. Name it SendRegistered and paste `https://sendregistered.com/mcp`.
3. Choose Connect and sign in to SendRegistered.

Works on claude.ai, the desktop app and mobile.

### ChatGPT

1. In ChatGPT, open Settings, then Apps and connectors, and add a custom connector.
2. Paste `https://sendregistered.com/mcp` and choose OAuth as sign-in.
3. Sign in to SendRegistered, then pick SendRegistered in a chat.

### Other assistants

Any client that supports a remote MCP server with OAuth can connect to:

```
https://sendregistered.com/mcp
```

That endpoint is Streamable HTTP. Sign-in uses OAuth 2.1 with PKCE. Public lookups (prices, products and registered-mail rules, no token) are also available at `https://sendregistered.com/mcp/public`.

On [Grok](https://grok.com/connectors), choose New Connector, then Custom, paste the URL and sign in.

Docs: https://sendregistered.com/developers/mcp  
OpenAPI: https://sendregistered.com/v1/openapi.json

## What the assistant can do

### Look up (no extra permission)

- `list_destinations` — destinations, products and prices
- `get_quote` — price of one letter
- `registered_mail_requirements` — whether a letter type must go by registered mail in DE, FR, BE, ES, CH, NL, GB or US

These three tools are also available, without a token, at `/mcp/public`.

### Send (`letters:write`)

- `upload_document` — store a PDF and check that it can be printed
- `create_order` — prepare the letter and show the price; nothing is charged
- `confirm_and_pay` — after you approve, pay from credit or return a checkout link
- `withdraw_order` — cancel and refund a paid letter that has not yet been handed to the post

### Track (`letters:read`)

- `get_order_status` — status, price and tracking number
- `get_proof_certificate` — proof facts of a posted letter

The send and track tools are documented at https://sendregistered.com/developers/mcp. They are not returned by `/mcp/public`.

## How you stay in control

The assistant shows the recipient, product, pages and price first. Nothing is posted until you approve. A connection can be limited to read access, or given a daily and monthly spend limit from prepaid credit. PDFs are stored encrypted in the EU and used only to print the letter.

Same prices as the website. Privacy policy: https://sendregistered.com/privacy. Terms: https://sendregistered.com/terms.

## Support

Questions: support@sendregistered.com or https://sendregistered.com/contact

## Publisher

SendRegistered (Inlef B.V.).

## License

MIT (this plugin package: manifests, logo and documentation only). The SendRegistered service itself is not open-sourced by this file.
