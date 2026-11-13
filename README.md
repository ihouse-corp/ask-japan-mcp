# Ask Japan — MCP server for Japan

Japanese company, invoice and postcode data, plus real people in Japan who make phone calls, reservations and errands for your AI agent.

- **MCP endpoint (Streamable HTTP, no API key):** `https://askjapan.senpinai.com/mcp`
- **Website:** https://askjapan.senpinai.com/
- **Official MCP Registry:** `com.senpinai/ask-japan`
- **Operator:** iHouse Co., Ltd. (iHouse株式会社), Osaka, Japan — corporate number 3120001180173
- **Privacy policy:** https://askjapan.senpinai.com/privacy

This repository holds documentation only. The server is hosted; there is nothing to install.

## Connect

**Claude (claude.ai / Claude Desktop):** Settings → Connectors → Add custom connector → paste `https://askjapan.senpinai.com/mcp`.

**ChatGPT (developer mode), Cursor, Cline, VS Code, any MCP client:**

```json
{
  "mcpServers": {
    "ask-japan": {
      "type": "streamable-http",
      "url": "https://askjapan.senpinai.com/mcp"
    }
  }
}
```

Clients that only speak stdio can use `npx mcp-remote https://askjapan.senpinai.com/mcp`.

## Tools

### Japanese public data (free, read-only)

| Tool | What it does |
|---|---|
| `search_company` | Search all ~5.8 million corporations registered in Japan by name (partial match, Japanese). |
| `get_company_profile` | Profile from a 13-digit corporate number: registered name, address, status, invoice registration. |
| `check_invoice` | Check whether a company is a registered Qualified Invoice Issuer (T-number). |
| `search_listed_companies` | Filter companies that file securities reports (EDINET) by industry. |
| `lookup_postcode` | Address for a 7-digit Japanese postcode, including large-office postcodes. |
| `search_address` | Find postcodes from part of an address or an office name. |

Sources: National Tax Agency corporate number and invoice publication data, Japan Post postcode data, FSA EDINET code list. Synced daily.

### People in Japan (MARU Japan Hands, paid)

| Tool | What it does |
|---|---|
| `list_services` | Services and prices: Japanese phone calls (¥1,500), restaurant and golf reservations (¥3,000), interpreting, in-store purchase and shipping, on-site photo checks, queue and pickup. |
| `check_availability` | Whether a new request can be taken now (JST 9:00–21:00). |
| `request_service` | Send a task. Fixed-price tasks are quoted immediately; others get a fixed quote within 2 hours. |
| `get_request_status` | Status, quote, payment and result (confirmation numbers, photos, receipts). |
| `quote_purchase` | Instant cost estimate to buy an item in Japan and ship it. |
| `get_menu`, `check_open`, `place_takeout_order` | Takeout from participating restaurants. |

Payment: JPYC, USDC or USDT (Kaia or Polygon); credit card coming soon. Full refund if the task cannot be done or is cancelled before work starts. Terms and seller details: https://hands.senpinai.com/legal

## Example prompts

- "Is 株式会社〇〇 a registered invoice issuer? Give me its corporate number and address."
- "Find the postcode for 大阪市北区梅田."
- "Call this restaurant in Osaka and book a table for 4 on Friday at 19:00."
- "How much would it cost to buy this item in Japan and ship it to Taiwan?"

## Contact

info@senpinai.com · https://hands.senpinai.com/contact
