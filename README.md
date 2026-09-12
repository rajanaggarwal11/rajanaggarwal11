### Rajan Aggarwal

I build infrastructure for TypeScript systems — tenant isolation, dependency resolution, transactional delivery. The layers where a failure doesn't announce itself.

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

**outbox-pg** — the transactional outbox pattern with a relay that isolates failures instead of stalling the queue behind one poison message. **drizzle-erd** — an entity-relationship diagram generated from a live schema rather than a stale diagram in a wiki.

---

Different layers, same problem: correctness where nothing errors. Every default in
these has a reason written next to it, usually because the alternative failed
quietly somewhere real first.
