# ACC 2026 Instructor Team — Claude Code Hooks + Skills Proposal

**Drafted by:** Thor Codex Oracle  
**Context:** Instructor-team chat says Claude Code is the primary tool; Alibaba/Qwen credit may support learners. One instructor asked whether their slot is a full 3 hours or includes opening/break.  
**Recommended format:** 3-hour advanced lab, adjustable to 2h20 content + 20m break + 20m share/Q&A.

## One-line positioning

> “จากใช้ Claude Code เป็น → สร้างระบบให้ Claude Code ทำงานซ้ำได้ ปลอดภัยขึ้น และสอนทีมต่อได้”

English:

> From using Claude Code to building repeatable, safe, teachable Claude Code workflows.

## Why this module fits ACC 2026

The chat direction already says Claude Code is the main tool. A normal intro class teaches prompts and setup. This advanced module teaches instructors how to build **courseware + operating system** around Claude Code:

- reusable skills for repeated teaching/workflow tasks
- hooks for deterministic safety and quality checks
- subagents for expert review without polluting main context
- tests and RRR as external truth and learning capture

This is appropriate for an instructor team because it creates materials they can reuse across cohorts.


## Learning outcomes for ACC 2026

By the end of the 3-hour lab, instructors/learners can:

| LO | Outcome | Evidence |
|---|---|---|
| LO1 | Explain when to use CLAUDE.md vs Skill vs Hook vs Subagent | filled guardrail map |
| LO2 | Draft a `SKILL.md` with trigger phrases, negative collisions, and verification | skill design card + trigger matrix |
| LO3 | Design a safe Claude Code hook with event, matcher, timeout, and remediation message | hook design card + payload observation |
| LO4 | Convert one workflow into teachable courseware | 5-slide mini deck outline + exit ticket |

## 3-hour agenda

| Time | Segment | Teaching point | Learner artifact | LO |
|---:|---|---|---|---|
| 0:00-0:10 | Opening: from prompt to system | prompt → CLAUDE.md → skill → hook → subagent | personal pain list | LO1 |
| 0:10-0:25 | Plan Mode + lean CLAUDE.md refresher | structure before coding; CLAUDE.md as lessons learned | one lesson candidate | LO1 |
| 0:25-0:50 | Skills anatomy | `SKILL.md`, `name`, `description`, trigger phrases | first skill draft | LO2 |
| 0:50-1:10 | Trigger accuracy clinic | positive triggers + negative collisions | trigger matrix | LO2 |
| 1:10-1:20 | Break | keep questions visible | — | — |
| 1:20-1:45 | Hooks mental model | deterministic guardrails; events/matchers | hook design card | LO3 |
| 1:45-2:10 | Hook lab | `PreToolUse` migration block or `PostToolUse` formatter | hook script + settings snippet | LO3 |
| 2:10-2:30 | Subagents + tests | isolated context + external truth | specialist-agent idea | LO1/LO3 |
| 2:30-2:45 | Presentation creation workflow | use AI to generate deck from lesson spine | 5-slide mini outline | LO4 |
| 2:45-3:00 | RRR close | convert learning into future skill/hook | retrospective + next action | LO4 |

## If actual slot is shorter

### 2 hours

- Keep Skills anatomy, trigger matrix, hook mental model, one hook design.
- Skip live hook implementation if setup is unstable.
- Homework: implement hook after class.

### 90 minutes

- Teach layer table.
- Draft one skill.
- Draft one hook design.
- Do not run hooks live.

### 60 minutes

- Treat as conceptual advanced appendix.
- Outcome: learners know when to use CLAUDE.md vs Skill vs Hook vs Subagent.

## Instructor demo script

### Demo 1 — Skill that catches real phrasing

Say to class:

> “The body of a skill is not the first thing Claude sees. The description is the gate.”

Create:

```bash
mkdir -p .claude/skills/release-checklist
$EDITOR .claude/skills/release-checklist/SKILL.md
```

Paste:

```markdown
---
name: release-checklist
description: Release checklist for shipping a project. Use when user says "release", "ship this", "deploy prod", or wants to publish a version. Do NOT trigger for local dev server or preview-only deploys.
argument-hint: "[staging|production]"
---

# Release Checklist

## Outcome
A release is ready only when tests, risk notes, rollback plan, and final evidence are present.

## Steps
1. Inspect git status and diff.
2. Identify changed behavior.
3. Run targeted tests.
4. Draft release notes.
5. Report Tested / Not-tested.
```

Then ask class which prompts should trigger:

- “ship this to prod” → yes
- “start local dev server” → no
- “make preview link” → no or clarify
- “rollback production” → yes
- “write PR description” → no

### Demo 2 — Hook as deterministic safety

Say:

> “CLAUDE.md can say do not edit migrations. A hook can actually stop it.”

Create `.claude/hooks/protect-migrations.py` and `.claude/settings.json` using the lab handout. Try editing `db/migrations/001.sql`. Show the block message.

### Demo 3 — Subagent boundary

Ask:

> “Would we put security review in CLAUDE.md, a Skill, a Hook, or a Subagent?”

Answer:

- Skill: checklist/workflow for security review
- Subagent: isolated reviewer context
- Hook: block obvious secret leaks
- CLAUDE.md: project-specific security conventions

## Qwen / multi-model note

If Qwen credits are available, position them as additional model capacity, not replacement for workflow design.

Exercise:

- Use Claude Code to orchestrate/code.
- Use Qwen or another model as second-opinion reviewer for the plan or trigger matrix.
- Compare review outputs using the same rubric.

Warning: do not make vendor comparison the main topic. The class goal is reusable workflow architecture.

## Instructor-team coordination

Recommended roles:

| Role | Responsibility |
|---|---|
| Lead instructor | explain mental model and run demos |
| Lab TA | help with paths, executable bits, JSON syntax |
| Reviewer | inspect skill descriptions and trigger matrices |
| Timekeeper | protect break and final RRR |

## Materials checklist

- `slides/siit/08-hooks-skills.md`
- `courses/siit-2025-12/advanced-hooks-skills-module.md`
- `courses/siit-2025-12/hooks-skills-facilitator-notes.md`
- `courses/siit-2025-12/materials/hooks-skills/README.md`
- `courses/siit-2025-12/materials/hooks-skills/worksheets.md`
- `.claude/skills/cc-workshop/SKILL.md`

## Message draft for ACC instructor chat

สรุป proposal สำหรับ slot Claude Code ขั้นสูงครับ:

> ผมเสนอให้หัวข้อเป็น “Hooks + Skills: จาก prompt เป็น workflow ที่ใช้ซ้ำและบังคับ quality ได้”  
> ถ้ามี 3 ชั่วโมง จะทำเป็น lab เต็ม: เขียน SKILL.md ของตัวเอง, ทำ trigger matrix, ออกแบบ hook, แล้วปิดด้วย RRR ว่าอะไรควรถูกยกระดับเป็น workflow ของทีม  
> ถ้าเวลาจริงเหลือ 90-120 นาที จะลด live hook implementation เหลือ hook design + demo แทน  
> แกนหลักคือ Claude Code เป็นตัวหลัก ส่วน Qwen credit ใช้เป็น reviewer/second opinion ได้ แต่ไม่ทำให้หัวข้อกลายเป็น vendor comparison

