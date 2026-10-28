The IntoDNS MCP Server (intodns-mcp) provides 45 direct Model Context Protocol tools to AI assistants, giving them live diagnostic capabilities for DNS records, email security, deliverability, blacklists, and BIMI standards without requiring an API key.
Below is the complete, ready-to-use configuration guide and overview for integrating and testing your fork.
Client Configuration (claude_desktop_config.json)
To connect the server to Claude Desktop, Cursor, or other MCP-compatible clients, add the following block to your client configuration file (e.g., ~/Library/Application Support/Claude/claude_desktop_config.json on macOS):
{
  "mcpServers": {
    "intodns": {
      "command": "npx",
      "args": ["-y", "intodns-mcp"]
    }
  }
}

Note: Restart your MCP client after updating the configuration.
Core Diagnostic Tool Categories (45 Tools Available)
The server exposes specialized tools grouped into functional diagnostic suites:
 * Live Domain Scans (scan_domain, nis2_quickscan): Fast, citation-backed checks assessing general configuration and regulatory compliance (such as NIS2 Article 21.2 readiness).
 * Email Deliverability & Security (check_sender_requirements, check_smtp_tls): Validates strict sender requirements for major providers (Google, Yahoo, Microsoft), SPF, DKIM, DMARC, and STARTTLS FCrDNS.
 * Reporting & Evidence Snapshots (get_everything_report, create_report_snapshot): Generates full structured JSON/Markdown reports and creates fixed, cryptographically hashed evidence snapshots for audit logs.
Local Testing & Development
If you are modifying or testing your fork locally before submitting your pull request, you can run the server directly via Node:
# Run via npx pointing to your local package or global install
npx -y intodns-mcp

