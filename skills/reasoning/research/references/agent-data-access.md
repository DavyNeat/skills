# Evaluating a way to give agents access to sensitive account data

Use when the user asks whether an agent (for example Fig, the EA) can safely read their finances, health, or other sensitive accounts.

## Ranking the options, safest first

1. **Read-only by protocol.** The credential itself cannot write, whatever the server does (example: SimpleFIN access URLs have no transfer or edit endpoint). A leaked key can only read.
2. **Official connector with OAuth scopes.** The vendor runs the MCP server, login happens in the browser, scopes are visible and revocable in the vendor's settings (example: Monarch's MCP connector). Grant read scope only.
3. **Unofficial server with a read-only flag.** The flag only hides write tools; the stored credential still has full power. Acceptable only self-hosted behind authentication.
4. **Unofficial server holding a password, TOTP secret, or session cookie.** Full account access, breaks when the vendor changes its web app, and often violates the vendor's terms. Recommend against.

## Points to cover in the answer

- Distinguish "read-only by design" from "read-only mode". The difference is what a stolen credential can do.
- Explain why read-only matters for agents: merchant names and memos are text other people write, so they can carry prompt injection. With no write tools, injection has nothing to act on.
- Name the risks that remain with read-only: data goes to the model provider, and the agent can repeat it in the wrong place.
- Route the connection through Executor (`executor-route` skill) so the user's approval policies apply. Check that Executor can host the server before promising it.
- When the user's current app has no API (example: Rocket Money), suggest keeping the app for what it does well and feeding the agent through a read-only source, with a one-time CSV export to backfill history.
- For paid connectors, check whether agent usage limits differ by plan tier. Limits can apply to reads as well as writes, and that changes which tier to recommend.
