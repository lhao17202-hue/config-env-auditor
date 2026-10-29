# Risk Rubric

Use this to prioritize config findings.

## High Risk

Flag as high risk when:

- secrets may be exposed to client bundles, logs, commits, or generated docs
- production defaults point to local, test, staging, or destructive services
- database, cache, queue, auth, payment, storage, or webhook settings are missing or ambiguous
- deployment requires undocumented secrets
- feature flags can enable incomplete or unsafe behavior
- migrations or workers run with different config from the web service
- environment-specific bug reports match config drift

## Medium Risk

Flag as medium risk when:

- `.env.example` is stale or incomplete
- variable names differ across code, CI, and deployment
- required variables lack startup validation
- default values are unclear
- docs omit preview/staging/test behavior
- deprecated variables remain in examples

## Low Risk

Flag as low risk when:

- comments are out of date but behavior is clear
- optional variables are undocumented but have safe defaults
- generated config changed without runtime effect
- unused example variables are harmless cleanup items

## Recommendation Style

For each risk, include:

- evidence path
- why it matters
- environment affected
- smallest safe fix
- verification command or check
