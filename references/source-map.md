# Source Map

Use this to discover where configuration is defined, loaded, overridden, and consumed.

## Files to Inspect

Look for:

- `.env`, `.env.*`, `.env.example`, `.env.sample`, `.env.local`, `.env.test`
- framework config such as `next.config.*`, `vite.config.*`, `nuxt.config.*`, `astro.config.*`, `django settings`, `rails credentials`, `spring application.yml`, `config/*.yaml`
- package and task scripts such as `package.json`, `Makefile`, `justfile`, `Taskfile`, `pyproject.toml`, `Cargo.toml`
- Docker and container files such as `Dockerfile`, `docker-compose*.yml`, `.dockerignore`
- CI/CD files such as `.github/workflows/*`, `.gitlab-ci.yml`, `azure-pipelines.yml`, `Jenkinsfile`
- deployment manifests such as Helm charts, Kubernetes YAML, Terraform, Pulumi, Serverless, Vercel, Netlify, Fly, Render, Railway, Heroku, Cloudflare, or AWS config
- runtime code that calls `process.env`, `os.environ`, `getenv`, `System.getenv`, `viper`, `dotenv`, `pydantic settings`, `convict`, or similar loaders

## Precedence Questions

Answer:

- What is the default value?
- Which file or platform overrides it?
- Does local development use the same variable name as CI or production?
- Is the value read at build time, startup time, request time, or job runtime?
- Does client-side code expose a variable that should stay server-only?
- Are worker, cron, migration, and web processes using the same config path?

## Evidence to Preserve

Record paths, line numbers when available, script names, command names, and deployment target names. If multiple sources conflict, quote the conflicting variable names and files rather than guessing silently.
