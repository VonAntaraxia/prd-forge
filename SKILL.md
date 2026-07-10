---
name: prd-forge
description: "Generate Product Requirements Documents (PRD). Two-phase: clarify via structured questions with lettered options, then write PRD to tasks/ with user stories and acceptance criteria."
homepage: https://github.com/VonAntaraxia/prd-forge
license: MIT
---

# PRD-Forge

Two phases: **Clarify** (questions) then **Forge** (PRD.md). Do NOT start implementing. Create the PRD.

## Clarify

**Core questions (ask what's missing, format with lettered options):**

1. **Problem:** What specific problem? Who experiences it?
   A. Improve onboarding
   B. Fix existing workflow gap
   C. New feature request
   D. Other: [specify]

2. **Users:** Who uses this?
   A. End users only
   B. Admins only
   C. Both
   D. Internal team only

3. **Core features:** Top 3 ranked. One must-have?
   A. Single feature, focused
   B. 2-3 features, phased
   C. Full feature set
   D. Unsure, propose

4. **Scope:** What's in? What's out?
   A. MVP only
   B. Full implementation
   C. Backend/API only
   D. UI only

5. **Timeline:** Deadlines? Phases?
   A. ASAP, no deadline
   B. 1 week
   C. 1 month
   D. Multi-phase

**Format questions like:** `1. [question]` then `A. [option]` / `B. [option]` on new lines indented. User can reply "1A, 2C, 3B" for quick iteration.

**Stop condition:** Generate after 5+ answers or user says "generate".

**Output:** Missing questions only. No explanations.

## Forge

Generate PRD after user answers. Save to `tasks/prd-[feature-name].md`.

**Sections:**

```markdown
# PRD: [Product Name]

## Problem Statement
[problem, audience, timing]

## Goals
- [measurable objective]

## User Stories
### US-001: [Title]
**Description:** As a [user], I want [feature] so that [benefit].
**Acceptance Criteria:**
- [ ] Specific verifiable criterion
- [ ] Typecheck/lint passes
- [ ] [UI stories] Verify in browser

### US-002: [Title]
...

## Functional Requirements
- FR-1: [action]: [outcome]
- FR-2: [action]: [outcome]

## Non-Goals (Out of Scope)
- [what this will NOT include]

## Technical Notes
[stack, integrations, data model]

## Success Metrics
- [metric]: [target]

## Timeline
- Phase 1: [date]: [deliverable]

## Open Questions
- [question]
```

**Rules:**
- Write to `tasks/prd-[feature-name].md`. Create `tasks/` if missing. Ask before overwrite.
- No filler sections. Use exact user feature names. If user says "no design", skip or write "TBD".
- User stories: small enough for one session, verifiable criteria, no vague. UI stories add "Verify in browser".
- Write for junior devs: explicit, avoid jargon, number reqs, concrete examples.

**Anti-slop check:** active voice, be specific, no filler/hand-holding/em-dashes/quotables. See stop-slop for full rules.

## Example

**User:** "Buat PRD untuk app catatan yang bisa sharing"

**Agent:**
> Questions:
> 1. Problem?
>    A. No existing note-sharing
>    B. Improve collaboration
>    C. Replace current tool
>    D. Other
> 2. Users?
>    A. Personal
>    B. Team
>    C. Both
> 3. Core features?
>    A. Notes + share only
>    B. + real-time edit
>    C. + permissions
> 4. Scope?
>    A. MVP only
>    B. Full
> 5. Timeline?
>    A. ASAP
>    B. 2 weeks
>    C. 1 month
