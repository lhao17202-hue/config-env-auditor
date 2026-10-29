# Config Env Auditor

Config Env Auditor is a Codex skill for auditing project configuration, environment variables, secrets expectations, feature flags, and runtime/deployment settings.

It helps developers understand why a project works in one environment and fails in another by mapping config sources, precedence, required variables, runtime differences, and deployment risks.

## Use Cases

Use this skill when you want Codex to:

- audit `.env` requirements and stale examples
- document configuration sources and precedence
- compare local, test, CI, staging, production, worker, and container settings
- find undocumented required secrets
- identify dangerous defaults or environment drift
- prepare deployment or debug environment-specific failures

Example prompt:

```text
Use $config-env-auditor to audit this repo's env vars, config sources, and deployment risks.
```

## Skill Metadata

```yaml
name: config-env-auditor
description: Audit project configuration, environment variables, secrets expectations, feature flags, and deployment/runtime settings. Use when onboarding to a repo, debugging environment-specific failures, preparing deployment, documenting .env requirements, or checking whether config changes may break local, CI, staging, or production behavior.
```

## Repository Structure

```text
.
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
|-- references/
|   |-- env-var-catalog.md
|   |-- output-templates.md
|   |-- risk-rubric.md
|   |-- runtime-matrix.md
|   `-- source-map.md
|-- scripts/
|   `-- validate_skill.py
|-- .github/
|   `-- workflows/
|       `-- validate.yml
|-- CONTRIBUTING.md
|-- LICENSE
`-- README.md
```

## Install

Clone this repository into your Codex skills directory:

```bash
git clone https://github.com/lhao17202-hue/config-env-auditor.git ~/.codex/skills/config-env-auditor
```

Windows PowerShell:

```powershell
git clone https://github.com/lhao17202-hue/config-env-auditor.git "$env:USERPROFILE\.codex\skills\config-env-auditor"
```

Restart Codex or reload skills if your environment does not detect new skills automatically.

## Validate

Run:

```bash
python scripts/validate_skill.py .
```

The validator checks required files, frontmatter, UI metadata, reference routing, unresolved placeholders, and the 350-character description limit.

## Design

The core `SKILL.md` stays concise. Source discovery, env var cataloging, runtime matrix guidance, risk prioritization, and output formats live in `references/`.

## License

MIT
