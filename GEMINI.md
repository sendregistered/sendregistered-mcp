# SendRegistered

SendRegistered lets you quote, send and track registered letters in Europe, the UK and the US from a PDF.

Connect at https://sendregistered.com/mcp. Gemini CLI signs in with OAuth on first use. Nothing is printed or charged until the user approves the letter. A connection can be limited to read access, or given a daily and monthly spend limit from prepaid credit.

## Tools

Lookup (no extra permission): `list_destinations`, `get_quote`, `registered_mail_requirements`.

Send (`letters:write`): `upload_document`, `create_order`, `confirm_and_pay`, `withdraw_order`.

Track (`letters:read`): `get_order_status`, `get_proof_certificate`.

Always show the recipient, product, pages and price before asking the user to approve. Same prices as the website.

Docs: https://sendregistered.com/developers/mcp
OpenAPI: https://sendregistered.com/v1/openapi.json
Support: https://sendregistered.com/contact
