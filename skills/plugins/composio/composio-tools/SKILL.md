---
name: composio-tools
description: Instructions and operational protocols for interacting with Composio-connected tools and SaaS integrations (GitHub, Slack, Jira, Notion, Linear, Gmail, etc.) via the Composio MCP server.
---

# Composio Integration Skill

This skill guides the discovery and invocation of actions across connected third-party tools authenticated through your Composio account.

## Overview
Composio exposes integrations dynamically through the Model Context Protocol (MCP) endpoint (`https://connect.composio.dev/mcp`). Available actions, schemas, and connected services reflect the integrations authenticated in your Composio dashboard.

## Tool Discovery & Execution Protocol

1. **Verify Authentication & Tool Availability:**
   - Ensure `COMPOSIO_API_KEY` is present in your environment variables.
   - Query available tools exposed by the `composio` MCP server. The available actions correspond directly to the tools enabled and connected in your Composio workspace.

2. **Action Execution Rules:**
   - Always confirm required parameters against the tool schema before executing an action.
   - For destructive operations (e.g., deleting records, sending external messages, modifying permissions), confirm intent or detail the target payload before firing.
   - If an action fails with an authorization error, verify the integration's connection status on the [Composio Dashboard](https://app.composio.dev).

3. **Fallback & Error Handling:**
   - **401/403 Authentication Failure:** Verify that `COMPOSIO_API_KEY` is set correctly in user environment variables and that the active session has not expired.
   - **Missing Integration:** If a requested service (e.g., GitHub, Slack) is unavailable in the tool list, guide the user to connect the application in their Composio dashboard.
