---
title: 08a Skills
description: 60-minute Skills-first variant
---

# 08a — Skills
<!-- .slide: id="part-a-skills" -->
## Reusable Claude Code Workflows

---

## Learning Outcomes

By the end, learners can:

1. Explain what a skill is and when to use one.
2. Draft a `SKILL.md` with a routing-focused description.
3. Test trigger phrases and negative collisions.
4. Use Boy's real skills as examples of shortcut vs domain specialist.

---

## Why Skills Exist

Repeated prompt = hidden workflow.

A skill turns that workflow into a reusable file Claude can load only when needed.

```
prompt once → CLAUDE.md if repeated → Skill if reusable
```

---

## Skill Is a Folder

```text
~/.claude/skills/<name>/SKILL.md      # global
.claude/skills/<name>/SKILL.md        # project
```

The body does not matter until the description routes correctly.

---

## Minimal SKILL.md

```yaml
--- # YAML frontmatter delimiter (example)
name: release-checklist
description: Make sure to use this skill whenever the user says "release", "ship", "deploy prod", or asks to publish a version. Do NOT trigger for local dev server.
argument-hint: "[staging|production]"
--- # YAML frontmatter delimiter (example)

# Release Checklist

## Outcome
## Steps
## Verification
```

---

## The Gate: Description

Claude sees the `description` before it sees the skill body.

Good description has:

1. purpose
2. literal trigger phrases
3. negative collisions
4. “Make sure to use...” when under-triggering is likely

---

## Polite vs Pushy

| Too polite | Better |
|---|---|
| `Helps with release tasks.` | `Make sure to use this skill whenever the user says "release", "ship", or "deploy prod".` |
| `Can review slides.` | `Use proactively when creating workshop slides or instructor notes.` |

Skills are invisible unless routing wins.

---

## Bad vs Good

| Bad | Why |
|---|---|
| `Debug things` | too broad |
| `Our workflow` | no trigger phrase |
| `Helps deploy` | no negative collision |

| Good |
|---|
| `Production deploy checklist. Use when user says "deploy prod", "release", or asks to ship. Do NOT trigger for preview deploys.` |

---

## Skill Body Template

```markdown
# Skill Name

## Outcome
What done means.

## Inputs
What to read or ask first.

## Steps
1. Inspect
2. Act
3. Verify

## Stop Conditions
When to stop or ask.

## Final Report
Tested / Not-tested / Risks
```

---

## Exercise — Pain to Skill

Pick one repeated task:

- write PR description
- prepare release
- deploy site
- make workshop slides
- debug failing tests
- summarize meeting notes

Write: name, purpose, trigger phrases, negative collisions, done means.

---

## Trigger Matrix

| Prompt | Should trigger? | Why |
|---|---|---|
| “ship this to prod” | yes | release intent |
| “start dev server” | no | local dev |
| “make preview link” | clarify | not production |
| “rollback production” | yes | incident path |
| “write PR desc” | no | other skill |

---

## Boy Demo 1 — `skill_ccc.md`

Path:

`ψ/digger-cc/evidence/boy-dna-package/skill_ccc.md`

Teaching point:

- minimum viable real skill
- literal triggers: `ccc`, `save context`, `context dump`
- repeated workflow → external memory

---

## Boy Demo 2 — `skill_peng-bookkeeping.md`

Path:

`ψ/digger-cc/evidence/boy-dna-package/skill_peng-bookkeeping.md`

Teaching point:

- Thai domain vocabulary routes better than generic English
- trigger examples: `เรียกพี่เปิ้ง`, `ทำตั้งเบิก`, `ภาษี`, `หัก ณ ที่จ่าย`
- skill as domain specialist, not only shortcut

---

## Boy Demo 3 — Invented Frontmatter

Open:

`skill_blacksheep.md`, `skill_elza.md`

Teaching point:

Users invent conventions before installers formalize them.

Do not punish this; extract the pattern, then standardize.

---

## Creation Paths

| Path | Best for |
|---|---|
| manual SKILL.md | teaching and transparency |
| `/create-shortcut` | fast personal shortcut |
| `skill-creator` | eval-driven distributed skill |
| registry/plugin | team or public distribution |

---

## Exit Ticket

Before leaving:

1. My skill name is:
2. It triggers when users say:
3. It must NOT trigger when:
4. Done means:
5. Verification evidence is:

---

## Homework

Install one personal skill and run the trigger matrix after using it three times.
