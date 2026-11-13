# Connect Ask Japan to Cline

Ask Japan is a hosted remote MCP server. There is no package to install, no local process to run, and no account, authentication or API key is required.

In Cline, open MCP Servers, then Configure MCP Servers. Merge this entry into the existing `mcpServers` object in the MCP settings JSON; preserve all other servers and settings:

```json
{
  "mcpServers": {
    "ask-japan": {
      "type": "streamableHttp",
      "url": "https://askjapan.senpinai.com/mcp"
    }
  }
}
```

Save the settings and connect. Confirm the server's tool list appears. For a free, read-only check, ask Cline to look up the Japanese postcode `5300001` using `lookup_postcode`.

The six data tools (`search_company`, `get_company_profile`, `check_invoice`, `search_listed_companies`, `lookup_postcode`, `search_address`) are free and read-only. Human services are paid per task from JPY 1,500; do not request or purchase a human service as an installation test.

Documentation: https://github.com/ihouse-corp/ask-japan-mcp
Operator: iHouse Co., Ltd., Osaka, Japan. Contact: info@senpinai.com.
