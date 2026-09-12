### Rajan Aggarwal

Developer tooling and product engineering — TypeScript, Postgres, and the machinery that keeps large monorepos honest.

---

#### Building

**[catalog-doctor](https://github.com/rajanaggarwal11/catalog-doctor)** · health check for pnpm workspaces

Finds the dependency drift a monorepo accumulates quietly — half-adopted catalogs, two versions of the same library, internal packages that can resolve to the registry, imports nothing declares — and fixes the ones that have a single correct answer. It declines the ones that need a human to pick a version, which is most of the point.

#### Next

Tooling for Postgres row-level security with Drizzle, and a transactional outbox for TypeScript. Both are pieces I got tired of rewriting.
