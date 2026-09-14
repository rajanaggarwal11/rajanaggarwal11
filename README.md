### Rajan Aggarwal

Infrastructure for TypeScript systems — what an AI agent is told, what an app tells the model, tenant isolation. The layers where a failure doesn't announce itself.

**[ctxlint](https://github.com/rajanaggarwal11/ctxlint)** — what are you actually sending the model? A local proxy that lints every request to Anthropic or OpenAI: unused tool definitions, cache misses and the character that broke them, secrets, injection in tool results. Never modifies a request. Run it on Claude Code and see 29 tools cost 26k tokens a turn.
`npx ctxlint wrap -- claude -p "hello"`

**[mcpcheck](https://github.com/rajanaggarwal11/mcpcheck)** — correctness checks for MCP servers. Reads exactly what the model reads and flags injected instructions, contract drift, and tools that hand the model a shell. Never calls a tool. Two of the eight most-downloaded servers on npm hand the model a terminal.
`npx mcpcheck node ./server.js`

**[pgrls](https://github.com/rajanaggarwal11/pgrls)** — Postgres row-level security you can actually verify. One assertion that asks Postgres which tables are exposed, and refuses to pass as a superuser.
`npm install pgrls` · `npx pgrls audit`

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** — health check for pnpm workspaces. Finds dependency drift and fixes what has a single correct answer.
`npx catalog-doctor` · [GitHub Action](https://github.com/rajanaggarwal11/catalog-doctor-action)

Next: a transactional outbox for Postgres.
