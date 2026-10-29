# Contributing

Contributions should make configuration audits more accurate, safer, and easier to act on.

## Good Contributions

- Add source discovery patterns for common frameworks or deployment platforms
- Improve env var catalog fields
- Clarify secret-safety rules
- Improve runtime matrix examples
- Strengthen validation checks

## Avoid

- Advice that encourages printing real secret values
- Generic deployment tutorials
- Unlinked reference files
- Placeholder TODO text
- Broad config rewrites without user approval
- Assuming production behavior without evidence

## Workflow

1. Edit `SKILL.md`, `references/`, or `scripts/`.
2. Run:

```bash
python scripts/validate_skill.py .
```

3. Keep core routing in `SKILL.md`; move detailed patterns and templates into `references/`.

## Review Checklist

- `SKILL.md` frontmatter has only `name` and `description`
- description includes capability and trigger context
- references are linked from `SKILL.md`
- no placeholder files remain
- validator passes
