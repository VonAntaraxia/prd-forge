# prd-forge

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat)
![GitHub Repo stars](https://img.shields.io/github/stars/VonAntaraxia/prd-forge?style=flat&logo=github)

Generate Product Requirements Documents. Two phases: clarify, then forge.

## Why prd-forge?

Writing PRDs from scratch takes time. Sections get skipped. Stories get vague. Criteria turn unverifiable.

prd-forge standardizes the process: asks structured questions first, then writes a complete PRD with measurable goals, verifiable acceptance criteria, and explicit non-goals.

## How it works

### 1. Clarify

Asks missing questions with lettered options:

1. **Problem** -- what specific problem?
2. **Users** -- who uses this?
3. **Core features** -- top 3 ranked, one must-have?
4. **Scope** -- what's in? what's out?
5. **Timeline** -- deadlines? phases?

Reply shorthand: `1A, 2C, 3B`. Generates after 5+ answers or "generate".

### 2. Forge

Writes `tasks/prd-[feature-name].md` with:

- Problem Statement
- Goals (measurable)
- User Stories with Acceptance Criteria
- Functional Requirements
- Non-Goals (explicit out-of-scope)
- Technical Notes
- Success Metrics
- Timeline
- Open Questions

Written for junior devs: explicit, no jargon, numbered reqs, concrete examples.

Anti-slop applies: active voice, specific, no filler, no hand-holding.

## Usage

Load the skill in your agent prompt:

```
<skill name="prd-forge">
```

Or reference the repo in skill config:

```json
{
  "skills": {
    "prd-forge": "github:VonAntaraxia/prd-forge"
  }
}
```

```bash
npx skills add https://github.com/VonAntaraxia/prd-forge --skill prd-forge --yes
```

## Files

- `SKILL.md` -- skill definition
- `AGENTS.md` -- agent behavior spec
- `references/example.md` -- PRD example

## License

MIT
