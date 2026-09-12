### Rajan Aggarwal

Correctness at the database boundary — multi-tenant isolation, row-level security, and the failures that pass every test.

---

#### Published

**[pgrls](https://github.com/rajanaggarwal11/pgrls)** · Postgres row-level security you can actually verify

RLS is the correct answer to tenant isolation, and it has three failure modes that all look like success. A policy does nothing to the table's **owner** unless it is `FORCE`d — and most applications connect as the owner of their own tables. Nothing applies to a **superuser**, so an audit run with migration credentials certifies a database it cannot see. And a custom setting reverts to `''` rather than unsetting, so the obvious predicate **raises** instead of denying, crashing every pooled request after the first.

`pgrls` defaults against all three, and `assertFullRlsCoverage` asks Postgres directly which tables are exposed — refusing to return a green report over a connection that bypasses policies, because a passing audit gathered there proves nothing.

Tested against Postgres 14 through 18.

```bash
npm install pgrls
```

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** · health check for pnpm workspaces

Half-adopted catalogs, two versions of one library, internal packages that can silently resolve to the registry, imports nothing declares. It fixes what has exactly one correct answer and refuses what needs a human to choose a version — a fixer that guesses is worse than one that declines.

```bash
npx catalog-doctor
```

With a [GitHub Action](https://github.com/rajanaggarwal11/catalog-doctor-action) for CI.

#### Next

A transactional outbox for Postgres and TypeScript, and an ERD generator for Drizzle schemas.

---

Every default in these has a reason written down next to it, usually because the
alternative failed quietly somewhere real first.
