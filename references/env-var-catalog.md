# Environment Variable Catalog

Use this to document `.env` requirements without exposing secrets.

## Fields

For each variable, capture:

- `Name`: exact variable name
- `Purpose`: what behavior it controls
- `Required`: yes, no, or environment-specific
- `Default`: documented default, code default, or none
- `Sensitive`: yes for secrets, tokens, credentials, connection strings, private keys, signing keys, webhooks, or production endpoints
- `Scope`: build, server runtime, client runtime, CI, test, worker, migration, cron, or deployment
- `Valid Values`: enum, boolean, URL, number range, path, JSON, comma-separated list, or opaque secret
- `Used By`: files, scripts, services, or jobs
- `Notes`: caveats, drift, or missing docs

## Sensitivity Rules

Do not print values from real `.env` files. Use placeholders such as:

- `DATABASE_URL=<postgres connection string>`
- `STRIPE_SECRET_KEY=<secret>`
- `JWT_SECRET=<random signing secret>`
- `PUBLIC_API_BASE_URL=<https URL>`

If a variable appears in client-side bundles or has public prefixes such as `NEXT_PUBLIC_`, `VITE_`, or `PUBLIC_`, mark it as public-facing and check that it is safe to expose.

## Documentation Checks

Flag:

- variables used in code but absent from `.env.example`
- variables in `.env.example` that are never read
- inconsistent names across scripts and CI
- required variables without validation
- secrets with unsafe dummy defaults
- production-only variables used by tests
