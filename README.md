# New Relic Observability MCP Server Manifest
[![Registry](https://img.shields.io/badge/MCP-Registry-orange)](https://github.com/modelcontextprotocol/registry)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This is the official Model Context Protocol (MCP) server for New Relic. It acts as a bridge between AI agents (like Claude Desktop, GitHub Copilot, or custom LLM orchestrators) and the New Relic Observability Platform.



By installing this server, your AI agents gain the ability to "see" and "act" on your telemetry data using natural language.

``
---

## 🚀 Capabilities

This server exposes high-level tools that allow AI models to perform complex observability tasks:

- **Entity & Account Intelligence**: Search for services, hosts, and mobile apps across your entire stack.
- **NRQL Power-User**: Execute any New Relic Query Language (NRQL) statement to fetch custom metrics, logs, and events.
- **Incident Response**: List active issues, acknowledge incidents, and retrieve root-cause analysis details.
- **Golden Metrics**: Automatically fetch the most important health indicators (Response Time, Error Rate, Throughput) for any entity.
- **Alerting**: Manage alert policies and conditions.
- **Change Tracking**: Correlate recent deployments with performance regressions.

---

## 🛠 Installation

This is a **Remote HTTP Server**. You do not need to download or compile code. To add this to your MCP-compatible client (like Claude Desktop), add the following to your configuration file:

### Configuration (e.g., `claude_desktop_config.json`)

```json
{
  "mcpServers": {
    "new-relic": {
      "url": "[https://mcp.newrelic.com/mcp/](https://mcp.newrelic.com/mcp/)",
      "type": "http",
      "headers": {
        "api-key": "YOUR_NEW_RELIC_USER_API_KEY",
        "include-tags": "discovery,alerting,nrql"
      }
    }
  }
}