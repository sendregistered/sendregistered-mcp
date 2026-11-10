# SendRegistered MCP

Send registered letters from your AI assistant. Quote a price, send a PDF and check delivery. You approve every letter before it is printed and handed to the post.

## Connect

- OAuth MCP (sign-in required for sending and tracking): `https://sendregistered.com/mcp`
- Public lookup (prices, products and registered-mail rules, no token): `https://sendregistered.com/mcp/public`
- Docs, including an Add to Cursor button: https://sendregistered.com/developers/mcp

Cursor snippet (also valid in `.cursor/mcp.json` or `~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "sendregistered": { "url": "https://sendregistered.com/mcp" }
  }
}
```

Add to Cursor deeplink:

```
cursor://anysphere.cursor-deeplink/mcp/install?name=sendregistered&config=eyJ1cmwiOiJodHRwczovL3NlbmRyZWdpc3RlcmVkLmNvbS9tY3AifQ==
```

On first connect, Cursor (and Claude, ChatGPT or Grok) asks you to sign in to SendRegistered and to choose what the assistant may do.

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
