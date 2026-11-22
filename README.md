I build small, well-tested tools for the parts of TypeScript systems that fail quietly: what an app sends to the model, and what Postgres lets each tenant see.

**[tokenwire](https://github.com/rajanaggarwal11/tokenwire)**: see exactly what your app sends to Anthropic or OpenAI, and lint it. On one Claude Code task, 27 of 29 tool definitions were never called and cost 22,302 tokens a turn. In CI, [its Action](https://github.com/rajanaggarwal11/tokenwire-action) comments on each pull request with the tokens it adds and the exact character that breaks the prompt cache.

**[pgrls](https://github.com/rajanaggarwal11/pgrls)**: one test that asks Postgres which tables a tenant can see past row-level security, including the table-owner bypass. It refuses to pass when run as a superuser.

**[pgoutbox](https://github.com/rajanaggarwal11/pgoutbox)**: a transactional outbox for Postgres. The test suite kills relays mid-delivery 24 times; no event is lost and every key stays in order.

**[mcpcheck](https://github.com/rajanaggarwal11/mcpcheck)**: lint an MCP server the way the model reads it: injected instructions, tools that run shell commands or code, and breaking changes to its tools.

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)**: find and fix dependency drift in pnpm workspaces.

Contact: [aggarwal11.rajan05@gmail.com](mailto:aggarwal11.rajan05@gmail.com)
