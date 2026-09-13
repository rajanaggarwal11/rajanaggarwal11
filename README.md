### Rajan Aggarwal

Infrastructure for TypeScript systems — tenant isolation, dependency resolution, transactional delivery. The layers where a failure doesn't announce itself.

**[pgrls](https://github.com/rajanaggarwal11/pgrls)** — Postgres row-level security you can actually verify. One assertion that asks Postgres which tables are exposed, and refuses to pass as a superuser.
`npm install pgrls` · `npx pgrls audit`

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** — health check for pnpm workspaces. Finds dependency drift and fixes what has a single correct answer.
`npx catalog-doctor` · [GitHub Action](https://github.com/rajanaggarwal11/catalog-doctor-action)

Next: a transactional outbox for Postgres, and an ERD generator for Drizzle schemas.
