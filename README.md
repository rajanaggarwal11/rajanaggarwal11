### Rajan Aggarwal

Infrastructure for TypeScript systems — what an AI agent is told, what an app tells the model, tenant isolation. The layers where a failure doesn't announce itself.

**[tokenwire](https://github.com/rajanaggarwal11/tokenwire)** — what are you actually sending the model? A local proxy that lints every request to Anthropic or OpenAI: unused tool definitions, cache misses and the character that broke them, secrets, injection in tool results. Never modifies a request. Run it on Claude Code and see 29 tools cost 26k tokens a turn. In CI it is size-limit for prompts: every PR gets the tokens it adds per request, the prompt-cache break to the character, and the cost — recorded offline, no API key.
`npx tokenwire wrap -- claude -p "hello"` · [GitHub Action](https://github.com/rajanaggarwal11/tokenwire-action)

**[mcpcheck](https://github.com/rajanaggarwal11/mcpcheck)** — correctness checks for MCP servers. Reads exactly what the model reads and flags injected instructions, contract drift, and tools that hand the model a shell. Never calls a tool. Two of the eight most-downloaded servers on npm hand the model a terminal.
`npx mcpcheck node ./server.js` · [GitHub Action](https://github.com/rajanaggarwal11/mcpcheck-action)

**[pgrls](https://github.com/rajanaggarwal11/pgrls)** — Postgres row-level security you can actually verify. One assertion that asks Postgres which tables are exposed, and refuses to pass as a superuser.
`npm install pgrls` · `npx pgrls audit` · [GitHub Action](https://github.com/rajanaggarwal11/pgrls-action)

**[pgrelay](https://github.com/rajanaggarwal11/pgrelay)** — a transactional outbox for Postgres that proves it. Events commit with your data or not at all, a late commit is never skipped, one event per key at a time across every relay — and the tests `kill -9` relays mid-delivery to show nothing is lost.
`npm install pgrelay` · `npx pgrelay status`

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** — health check for pnpm workspaces. Finds dependency drift and fixes what has a single correct answer.
`npx catalog-doctor` · [GitHub Action](https://github.com/rajanaggarwal11/catalog-doctor-action)

Available for audits — Postgres tenant isolation, event delivery, MCP servers, what your agents send. [aggarwal11.rajan05@gmail.com](mailto:aggarwal11.rajan05@gmail.com)
