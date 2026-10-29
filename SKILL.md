---
name: config-env-auditor
description: Audit project configuration, environment variables, secrets expectations, feature flags, and deployment/runtime settings. Use when onboarding to a repo, debugging environment-specific failures, preparing deployment, documenting .env requirements, or checking whether config changes may break local, CI, staging, or production behavior.
---

# Config Env Auditor

## Core Workflow

Map how configuration reaches runtime, then identify missing documentation, dangerous defaults, environment drift, and deployment risks. Prefer evidence from files and scripts over assumptions.

1. Inventory config sources: `.env*`, examples, package scripts, Docker files, compose files, CI workflows, deployment manifests, framework config, secret references, and runtime loaders.
2. Trace precedence: defaults, local overrides, CI variables, staging/production secrets, command-line flags, feature flags, and generated config.
3. Extract environment variables and settings with purpose, required/optional status, default value, sensitivity, valid values, and where each is consumed.
4. Compare environments: local, test, CI, staging, production, workers, cron jobs, and containers.
5. Flag risks: missing `.env.example`, undocumented required secrets, unsafe defaults, mismatched names, dead variables, unguarded production behavior, and config drift.
6. Produce concise Markdown docs or an audit report the next developer can use before running, testing, or deploying the project.

## Reference Routing

Load only what matches the task:

- For finding config sources and precedence, read `references/source-map.md`.
- For documenting environment variables, read `references/env-var-catalog.md`.
- For comparing local, CI, staging, and production behavior, read `references/runtime-matrix.md`.
- For prioritizing findings and safety risks, read `references/risk-rubric.md`.
- For final report formats, read `references/output-templates.md`.

## Rules

- Never print or ask for real secret values. Document names, purposes, and expected shape only.
- Mark inferred behavior as inferred when no authoritative source exists.
- Do not change deployment or secret configuration unless the user explicitly asks.
- Preserve existing hand-written config comments and docs when generating updates.
- Prefer incremental documentation updates over replacing entire environment docs.
- When config execution cannot be verified, include the exact commands or environment checks the user should run.

## Output Contract

Return:

- `Config Sources`: files, tools, loaders, and precedence found.
- `Environment Variables`: required, optional, sensitive, defaulted, unused, or undocumented variables.
- `Runtime Matrix`: differences across local, test, CI, staging, production, workers, and containers.
- `Risks`: prioritized config drift, dangerous defaults, missing docs, or deployment hazards.
- `Recommended Updates`: documentation, `.env.example`, validation, or test changes.
- `Verification`: commands run or checks still needed.
