# Output Templates

Use these formats for audit results.

## Audit Report

```markdown
**Config Sources**
- `<path>`: <role and precedence>

**Environment Variables**
| Name | Required | Sensitive | Scope | Default | Used By | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| `NAME` | yes/no | yes/no | runtime/build/CI | `<default or none>` | `<path>` | <notes> |

**Runtime Matrix**
| Environment | Source | Required Vars | Command | Risk |
| --- | --- | --- | --- | --- |
| local | `.env.local` | `...` | `...` | `...` |

**Risks**
1. High - <finding> because <impact>. Evidence: `<path>`.
2. Medium - <finding> because <impact>. Evidence: `<path>`.

**Recommended Updates**
- <docs, validation, .env.example, CI, deployment, or test update>

**Verification**
- `<command>`: <result or why it should be run>
```

## Compact Report

```markdown
Must fix:
- <risk and evidence>

Should document:
- <variable or config source>

Commands:
- `<command>`
```

## Documentation Update Targets

Prefer these names when creating docs:

- `CONFIG-MAP.md`
- `ENV-VARS.md`
- `RUNTIME-MATRIX.md`
- `CONFIG-RISK.md`

Preserve existing project documentation names if the repository already has a convention.
