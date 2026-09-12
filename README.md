### Rajan Aggarwal

I ship products end to end, and open-source the parts I got tired of rewriting.

---

#### Published

**[pgrls](https://github.com/rajanaggarwal11/pgrls)** · Postgres row-level security you can actually verify

Policies declared beside the table, tenant context that cannot leak across a connection pool, and one assertion that asks Postgres whether every table is really protected — then names the ones that aren't. It refuses to return a green report over a superuser connection, because RLS is never applied to one and a passing audit gathered there proves nothing at all.

```bash
npm install pgrls
```

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** · health check for pnpm workspaces

Finds the dependency drift a monorepo accumulates quietly — half-adopted catalogs, two versions of the same library, internal packages that can resolve to the registry, imports nothing declares. It fixes what has a single correct answer and declines what needs a human to choose a version, which is most of the point.

```bash
npx catalog-doctor
```

There's a [GitHub Action](https://github.com/rajanaggarwal11/catalog-doctor-action) for running it in CI.

#### Next

A transactional outbox for Postgres and TypeScript, and an ERD generator for Drizzle schemas. Both are pieces I got tired of rewriting.
