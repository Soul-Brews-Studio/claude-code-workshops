# Hooks + Skills
## จาก prompt → workflow → guardrail

**Advanced module สำหรับ Claude Code workshop**

---

## Learning Goal

หลังจบ module นี้ ผู้เรียนจะทำได้ 3 อย่าง:

1. แยกได้ว่าอะไรควรอยู่ใน **CLAUDE.md / Skill / Hook / Subagent**
2. เขียน **SKILL.md** ที่ trigger แม่น ไม่แย่งงาน skill อื่น
3. ออกแบบ **Hooks** ที่กันพลาดแบบ deterministic โดยไม่ทำให้ workflow ติดขัด

---

## Mental Model

| Layer | Nature | ใช้เมื่อ |
|---|---|---|
| **CLAUDE.md** | advisory memory | context, convention, lessons learned |
| **Skill** | reusable workflow | ขั้นตอนที่เรียกซ้ำ / domain knowledge |
| **Hook** | deterministic automation | สิ่งที่ต้องเกิดทุกครั้ง / ห้ามพลาด |
| **Subagent** | isolated specialist | งานค้นคว้า / review / debug ที่ใช้ context เยอะ |

> ถ้าอยากให้ AI “รู้” → CLAUDE.md / Skill  
> ถ้าอยากให้ระบบ “บังคับ” → Hook

---

## Why This Matters

คนส่วนใหญ่เริ่มจาก prompt ยาว ๆ:

> “ช่วยเช็ค style, ห้ามแก้ migration, run test ก่อนบอกว่าเสร็จ, แล้วทำตาม pattern เดิม...”

ปัญหา: ลืมบอก, AI อ่านไม่ครบ, context เต็ม, ทำซ้ำทุก session

**Solution:** compile behavior into layers

---

## The Compiler Ladder

```
ครั้งที่ 1: prompt สด
ครั้งที่ 2: จดใน CLAUDE.md
ครั้งที่ 3: ทำเป็น Skill
ถ้าห้ามพลาด: ทำเป็น Hook
ถ้าใช้ context เยอะ: ทำเป็น Subagent
```

นี่คือการเปลี่ยนจาก “prompting” เป็น “operating system”

---

## Navigate
<!-- .slide: id="navigate" -->

Choose delivery path:

| Slot | Start | Include | Stop |
|---|---|---|---|
| 60m Skills | `#/part-a-skills` | skills + trigger matrix + Boy demo | `#/homework` |
| 90m Hooks | `#/part-a-skills` | skills + hooks + lab | `#/homework` |
| 3h ACC | `#/part-a-skills` | all parts + presentation creation + quiz | `#/homework` |

Anchors: `#/part-a-skills`, `#/part-b-hooks`, `#/part-c-compose`, `#/part-d-presentation`, `#/boy-demo`, `#/homework`

---

# Part A — Skills
<!-- .slide: id="part-a-skills" -->
## reusable workflows that load on demand

---

## Skill คืออะไร

Skill = โฟลเดอร์ที่มี `SKILL.md`

```
~/.claude/skills/deploy-checklist/SKILL.md   # user/global
.claude/skills/project-release/SKILL.md      # project/team
```

Claude โหลด skill เฉพาะเวลาที่ตรง intent → ไม่กิน context ทุก session

---

## SKILL.md Anatomy

```yaml
--- # YAML frontmatter delimiter (example)
name: deploy-checklist
description: Production deploy checklist. Use when user says "deploy", "release", or wants to ship to production. Do NOT trigger for local dev server.
argument-hint: "[staging|production]"
--- # YAML frontmatter delimiter (example)

# Deploy Checklist

## Preflight
- [ ] tests pass
- [ ] rollback plan exists
```

---

## The Gate: `description`

Claude เห็น `description` ก่อน body

ถ้า description ไม่แม่น → skill ไม่ถูกโหลด

**สูตรที่ใช้ได้จริง:**

```text
<Purpose in one line>.
Use when user says "phrase 1", "phrase 2", or wants to <intent>.
Do NOT trigger for <collision> (use /other-skill).
```

---

## Bad vs Good Description

| Bad | Why bad |
|---|---|
| `Help with deployment` | กว้างเกินไป ไม่มี trigger phrase |
| `Debug things` | แย่งงานทุกอย่าง |
| `Our workflow` | Claude ไม่รู้ว่าเมื่อไหร่ควรใช้ |

| Good | Why good |
|---|---|
| `Production deploy checklist. Use when user says "deploy prod", "release", or asks to ship. Do NOT trigger for preview deploys (use /preview).` | มี intent + phrases + negative space |

---

## Skill Body Pattern

ให้ body เป็น **playbook** ไม่ใช่ essay

```markdown
# Skill Name

## Outcome
What done means.

## Required Inputs
What to ask/read before acting.

## Steps
1. Inspect...
2. Edit...
3. Verify...

## Stop Conditions
When to stop / ask / refuse.

## Output
What to report back.
```

---

## Exercise 1 — Turn Pain into Skill

เลือก pain ที่เจอบ่อย:

- เขียน PR description
- release checklist
- debug failing tests
- deploy to Cloudflare
- summarize meeting notes
- prepare workshop slides

เขียน 3 บรรทัด:

1. Trigger phrases ที่มนุษย์พูดจริง
2. Negative collisions
3. Done means what?

---

## Exercise 1 Template

```markdown
--- # YAML frontmatter delimiter (example)
name: <slug>
description: <purpose>. Use when user says "...", "...", or wants to .... Do NOT trigger for ... (use /...).
argument-hint: "[optional]"
--- # YAML frontmatter delimiter (example)

# /<slug>

## Outcome

## Steps

## Verification

## Final Report
```

---

## Skill Maturity Tiers

Soul Brews convention:

| Tier | Meaning |
|---|---|
| `[core]` | stable identity/workflow primitive |
| `[standard]` | mature, reusable |
| `[lab]` | experimental |
| `[digger]` | Digger-specific excavation workflow |
| `[zombie]` | legacy compatibility |

Use tiers as a reading signal, not as official Anthropic metadata.

---

## Creation Paths

| Path | Best for | Tradeoff |
|---|---|---|
| `/create-shortcut` | fast personal/project workflow | quick, less tested |
| official `skill-creator` | distributed skills | slower, eval-driven |
| manual `mkdir + SKILL.md` | teaching / controlled demo | transparent |

Workshop recommendation: teach manual first, then show automation.

---

## Boy / Pinyo Demo

Use Boy’s DNA package as living proof:

- `skill_ccc.md` — simple hand-rolled skill shape
- `skill_peng-bookkeeping.md` — Thai trigger phrases + domain-specific routing
- Discussion: why did Boy invent `installer: manual`?

Point: conventions emerge when people reuse workflows.

---

# Part B — Hooks
<!-- .slide: id="part-b-hooks" -->
## deterministic guardrails

---

## Hook คืออะไร

Hook = command ที่ Claude Code เรียกเมื่อเกิด event

ใช้สำหรับสิ่งที่ต้องเกิด **ทุกครั้ง**:

- format หลัง edit
- block secret leak ก่อน push
- ห้ามแก้ migrations
- log commands for audit
- remind verification before stop

---

## CLAUDE.md vs Hook

| CLAUDE.md | Hook |
|---|---|
| “กรุณารัน prettier” | runs prettier |
| “ห้ามแก้ migrations” | blocks Edit/Write to migrations |
| “อย่าลืม test” | blocks Stop until test evidence exists |
| advisory | deterministic |

Rule: ถ้าพลาดแล้วเสียหาย → Hook

---

## Hook Config Shape

`.claude/settings.json` or `~/.claude/settings.json`

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "$CLAUDE_PROJECT_DIR/.claude/hooks/format.sh",
            "timeout": 30
          }
        ]
      }
    ]
  }
}
```

---

## Core Events

| Event | When |
|---|---|
| `PreToolUse` | before tool executes — can block risky action |
| `PostToolUse` | after successful tool — feedback/format/log |
| `UserPromptSubmit` | before prompt enters model — route/inject context/block |
| `Stop` | before Claude stops — enforce completion gates |
| `SubagentStop` | before subagent stops — enforce worker report |
| `Notification` | when Claude needs attention |
| `PreCompact` | before compaction — checkpoint state |

---

## Matcher Rules

For `PreToolUse` / `PostToolUse`:

```json
"matcher": "Edit|Write|MultiEdit"
```

- exact string: `Write`
- regex: `Edit|Write`
- wildcard: `*`
- omit matcher for events like `Stop` or `UserPromptSubmit`

---

## Hook Input/Output Model

Hooks receive JSON on stdin.

They can:

1. exit `0` and allow
2. print feedback to stderr/stdout
3. return structured JSON to block or add context

Example block shape:

```json
{
  "decision": "block",
  "reason": "Do not edit migration files directly. Create a new migration."
}
```

---

## Hook Example 1 — Protect Migrations

`.claude/hooks/protect-migrations.py`

```python
#!/usr/bin/env python3
import json, sys
payload = json.load(sys.stdin)
path = str(payload.get("tool_input", {}).get("file_path", ""))
if "/migrations/" in path:
    print("Migration files are immutable. Create a new migration.", file=sys.stderr)
    print('{"decision":"block","reason":"Migration files are immutable."}')
    sys.exit(0)
```

Use as `PreToolUse` for `Edit|Write|MultiEdit`.

---

## Hook Example 2 — Format After Edit

`.claude/hooks/format-after-edit.sh`

```bash
#!/usr/bin/env bash
set -euo pipefail

if command -v prettier >/dev/null 2>&1; then
  prettier --write . >/dev/null
fi
```

Use as `PostToolUse`.

Warning: make it fast. Slow hooks make agents hate the project.

---

## Hook Example 3 — Stop Gate

Purpose: do not let agent claim done without evidence.

```python
#!/usr/bin/env python3
import json, pathlib, sys
state = pathlib.Path(".claude/state/last-test.txt")
if not state.exists():
    print("Before stopping, run targeted tests or record Not-tested.", file=sys.stderr)
    print('{"decision":"block","reason":"Missing verification evidence."}')
```

Use sparingly. Blocking Stop can be powerful and annoying.

---

## Hook Design Rule: Feedback > Friction

Prefer:

- fast checks
- clear error messages
- local project scripts
- allowlist over broad shell magic
- `PostToolUse` feedback before blocking

Avoid:

- long-running hooks
- network calls on every edit
- hooks that rewrite large areas unexpectedly
- blocking while Claude is mid-plan

---

## Safety Ladder

| Risk | Hook behavior |
|---|---|
| Low | log or warn |
| Medium | auto-fix after action |
| High | block before action |
| Critical | block + human approval path |

Example: formatter = auto-fix; secret leak = block.

---

# Part C — Compose Them
<!-- .slide: id="part-c-compose" -->

---

## Skill + Hook Pairing

| Skill | Hook |
|---|---|
| `/deploy` checklist | block deploy if tests missing |
| `/db-migration` playbook | block direct edits to old migrations |
| `/course-slide` writer | run markdown lint / link check |
| `/rrr` retrospective | Stop hook checks retrospective exists |
| `/security-review` | PreToolUse blocks secret files |

Skill teaches the workflow. Hook enforces invariants.

---

## Subagents Fit Here

Use subagents when work needs separate context:

- `course-designer` drafts agenda
- `hook-reviewer` audits settings risk
- `skill-evaluator` tests trigger prompts
- `security-reviewer` checks hooks for unsafe shell

The main agent remains conductor.

---

## Exercise 2 — Build Guardrail Map

For your project, list 5 repeated failures:

| Failure | Layer |
|---|---|
| forgot tests | Stop hook or skill checklist |
| used wrong API version | Context7 / docs skill |
| edited generated file | PreToolUse hook |
| PR description weak | skill |
| security issue missed | subagent + hook |

Then choose only **one** to implement today.

---

## Exercise 3 — Trigger Test Matrix

For every skill, write prompts:

| Prompt | Should trigger? |
|---|---|
| “deploy prod” | yes |
| “start dev server” | no |
| “release staging preview” | maybe — clarify |
| “rollback production” | yes |

If you cannot write this table, description is not ready.

---

## Instructor Live Demo

1. Open a tiny project
2. Create `.claude/skills/release-checklist/SKILL.md`
3. Ask: “ship this” → inspect whether skill should trigger
4. Add `.claude/hooks/protect-migrations.py`
5. Try editing `migrations/001.sql`
6. Show block message
7. Discuss: what belongs in skill vs hook?

---

## Advanced Pattern — Hook Observability

Create `.claude/hooks/log-event.py`:

- append event name
- append tool name
- append paths touched
- never store secrets

Then run retrospective from real event logs.

This makes Claude Code workflows measurable.

---

## Advanced Pattern — Team Policy

Project `.claude/settings.json` = shared team policy

User `~/.claude/settings.json` = personal preferences

Local `.claude/settings.local.json` = experiments / machine-specific

Teach students: commit shared guardrails, never commit secrets.

---

## Anti-Patterns

- 800-line CLAUDE.md with every rule ever
- skill descriptions that say only “helps with X”
- hooks that run full test suite after every edit
- blocking hooks with vague messages
- subagents with all tools and no scope
- creating 20 skills before observing real usage

---

## The Course Arc

```
Prompt → CLAUDE.md → Short Code → Skill → Hook → Subagent → Team Workflow
```

Students should feel: “I can build a personal AI operating system.”

---

## Final Checklist

Before shipping a skill:

- [ ] name matches directory
- [ ] description has trigger phrases
- [ ] negative collisions named
- [ ] body has outcome / steps / verification
- [ ] 5 trigger tests written

Before shipping a hook:

- [ ] event is correct
- [ ] matcher is narrow
- [ ] command is fast
- [ ] failure message tells Claude what to do next
- [ ] secrets are not logged

---

## Key Takeaways

1. **Skills** package knowledge and workflow
2. **Hooks** enforce invariants
3. **Subagents** isolate specialist context
4. Good systems start from repeated pain, not from clever abstractions
5. The best prompt is the one you never type again

---

# Part D — Presentation Creation
<!-- .slide: id="part-d-presentation" -->
## turn workflow into teachable courseware

---

## Deck Pipeline Pattern

Use the Soul Brews / Phukhao pattern:

```
lesson spine
  ↓
slide outline
  ↓
paired markdown/html deck
  ↓
lab handout + worksheet
  ↓
quiz / evaluation
  ↓
RRR after delivery
```

Evidence patterns: `claude-code-workshops/slides/siit/NN-name.md` + `.html`; Phukhao course folders include `slides.md`, `syllabus.md`, `quiz.html`, `evaluation-10-questions.md`, `image-prompts.md`, and audio.

---

## Presentation Prompt Recipe

A strong slide-generation prompt specifies:

- audience and duration
- visual style and fonts
- slide count
- language mix
- per-slide title, message, and visual metaphor
- what NOT to make technical

Reference pattern: Nat's `gemini-slide-prompt-v6.md` starts from theme, audience, duration, language, design specs, then slide-by-slide content.

---

## Corporate Alternative: PPTX Skill

For corporate clients, a markdown/HTML deck may not be enough.

Offer two paths:

| Path | Best for | Output |
|---|---|---|
| Reveal/HTML | web workshop, technical learners | `.md` + `.html` |
| PPTX skill | corporate handoff, editable client deck | `.pptx` |

Teach the workflow first; choose output format last.

---

## Triggering: Polite vs Pushy

Anthropic skill-creator lesson: Claude often **under-triggers** skills.

| Too polite | Better |
|---|---|
| `Helps with release tasks.` | `Make sure to use this skill whenever the user says "release", "ship", "deploy prod", or asks to publish a version.` |
| `Can review slides.` | `Use this skill proactively when creating workshop slides, course outlines, or instructor notes.` |

Be explicit. Skills are invisible unless the description wins the routing decision.

---

## Six Boy Demo Callouts
<!-- .slide: id="boy-demo" -->

| File | Slide use | Teaching point |
|---|---|---|
| `skill_ccc.md` | minimum viable SKILL.md | repeated workflow → skill |
| `skill_peng-bookkeeping.md` | ACC live demo | Thai domain trigger accuracy |
| `skill_blacksheep.md` | invented frontmatter | users create conventions |
| `skill_elza.md` | personality fallback | graceful voice switching |
| `index.html` | architecture diagram | package as distributable DNA |
| `PROVENANCE.md` | evidence handling | frozen snapshots matter |

Open files live from `ψ/digger-cc/evidence/boy-dna-package/`.

---

## Boy Demo Callout 1 — `skill_ccc.md`

Path:

`digger-oracle.wt-1-cc-workshop-skills/ψ/digger-cc/evidence/boy-dna-package/skill_ccc.md`

Why it is perfect for class:

- short, readable hand-rolled skill
- has real trigger phrases: `ccc`, `save context`, `context dump`
- turns a repeated workflow into a reusable command
- shows Boy independently rediscovered the pattern

---

## Boy Demo Callout 2 — `skill_peng-bookkeeping.md`

Path:

`digger-oracle.wt-1-cc-workshop-skills/ψ/digger-cc/evidence/boy-dna-package/skill_peng-bookkeeping.md`

Why it is advanced:

- Thai domain triggers: `เรียกพี่เปิ้ง`, `ทำตั้งเบิก`, `ภาษี`, `หัก ณ ที่จ่าย`
- file naming convention and domain workflow
- exact tax-form deadlines and output format
- demonstrates skill as domain expert, not just shortcut

---

## Presentation Exercise

Turn your skill into five teaching slides:

| Slide | Content |
|---:|---|
| 1 | pain story |
| 2 | mental model |
| 3 | file format |
| 4 | bad vs good |
| 5 | exercise / exit ticket |

Rule: every deck must point to a real artifact learners can open.

---

## Homework
<!-- .slide: id="homework" -->

Tonight:

1. Write one personal skill from a repeated task
2. Add one non-blocking hook that logs or formats
3. Run one trigger test matrix
4. Write one RRR: what should become a skill next?

