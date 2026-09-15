# Copilot cloud-agent MCP instructions

- For Jira data, call the tools exposed by the `atlassian-rovo` MCP server directly.
- The Jira site is `https://premiertechdigital.atlassian.net`; use that site when a Rovo tool requires site context.
- `COPILOT_MCP_` secrets and variables are private to MCP server configuration. They are intentionally unavailable to the agent shell and setup scripts.
- Never inspect, print, decode, or request `COPILOT_MCP_` values from the user.
- Never claim that `COPILOT_MCP_JIRA_SITE_URL`, `COPILOT_MCP_JIRA_USER_EMAIL`, or `COPILOT_MCP_JIRA_API_TOKEN` is required. This repository authenticates Rovo through `COPILOT_MCP_ATLASSIAN_BASIC_AUTH` in the MCP configuration.
- If Jira tools are absent, report that the `atlassian-rovo` MCP server did not start and direct maintainers to the cloud-agent session's **Start MCP Servers** log. Do not diagnose this as missing shell environment variables.
- If a Jira tool returns an authentication or authorization error, report the exact tool error without exposing credentials.
