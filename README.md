# Uber Eats MCP server for ChatGPT and Claude

Connect Uber Eats Manager to ChatGPT, Claude, Codex and Claude Code through Cotlet.dev. Uber Eats APIs for restaurants may require written approval; Cotlet provides a hosted MCP connection to your own merchant account through a signed-in Cloud Browser.

## What you can ask

- List stores and check which are taking orders.
- Read menus, mark an item sold out or change one price after your approval.
- Review and update holiday hours without losing existing exceptions.
- Inspect orders, accept or deny them, and review canceled orders.

## Connect in 2 minutes

Get your API key at https://cotlet.dev/app and export it as `COTLET_API_KEY`.

### Claude Code

```bash
claude mcp add --transport http cotlet https://cotlet.dev/mcp/v1 --header "Authorization: Bearer $COTLET_API_KEY"
```

### ChatGPT

Settings -> Apps & Connectors -> Create. Set the MCP server URL to `https://cotlet.dev/mcp/v1`, then sign in with Cotlet.dev.

### Cursor

Copy `.cursor/mcp.json` from this repo into your project.

## Run it locally (stdio)

This repository includes a small Python stdio bridge. It lists its Uber Eats browser tools without a key and forwards calls to Cotlet.dev. The hosted URL above remains the recommended connection.

```json
{"mcpServers":{"uber-eats":{"command":"uvx","args":["uber-eats-mcp"],"env":{"COTLET_API_KEY":"your-key"}}}}
```

Tools: `uber_eats_guide`, `uber_eats_status`, `uber_eats_open`, `uber_eats_read`, `uber_eats_click`, `uber_eats_type`, `uber_eats_close`.

## Questions from Uber Eats users

**Does Uber Eats have an MCP server or API for restaurants?** Uber documents Eats APIs for menus, orders and stores, and access may require written approval. Cotlet provides a hosted MCP server for your signed-in merchant account.

**Can an agent pause a store or change a menu?** Yes. Write actions ask for your approval by default, including store status, holiday hours and menu changes.

**Where do I start?** Sign in to Uber Eats Manager in Cotlet Cloud Browser, enable Uber Eats for agents, then connect `https://cotlet.dev/mcp/v1`.

## Find it on

- [Uber Eats integration reference](https://cotlet.dev/integrations/uber-eats-api-mcp-server?utm_source=github&utm_medium=readme&utm_campaign=uber-eats)
- [Request access](https://cotlet.dev/signup?app=uber-eats)
- [Cotlet.dev console](https://cotlet.dev/app)

Licensed under Elastic License 2.0. See LICENSE.
