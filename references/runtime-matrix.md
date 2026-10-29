# Runtime Matrix

Use this when comparing behavior across environments.

## Environments

Consider:

- local development
- test
- CI
- preview deployments
- staging
- production
- web server
- worker or queue process
- cron or scheduled jobs
- migrations or one-off scripts
- Docker/container runtime

## Matrix Columns

Useful columns:

- environment or process
- config source files
- required variables
- build-time variables
- runtime variables
- secret provider
- database/cache/queue endpoints
- feature flags
- command used to start
- known differences and risks

## Drift Patterns

Flag when:

- CI has variables not documented for local setup
- production requires secrets not present in deployment docs
- Docker uses different variable names than app code
- tests rely on production-like defaults
- build-time variables are expected to change at runtime
- workers require variables omitted from web process docs
- preview/staging points at production services
- feature flags differ without an owner or expiry

## Verification

Recommend commands such as config validation scripts, dry-run builds, type checks, CI workflow checks, container config inspection, or app-specific config doctor commands when they exist.
