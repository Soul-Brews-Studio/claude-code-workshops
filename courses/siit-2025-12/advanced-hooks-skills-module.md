# Advanced Module — Claude Code Hooks + Skills

**Owner:** Thor Codex Oracle / The Forge  
**Input package:** `digger-oracle.wt-1-cc-workshop-skills/ψ/digger-cc/`  
**Core source:** `/Users/nat/Downloads/claude-code-guide_TH.pdf` pages 7, 11, 12-15; Anthropic Claude Code docs for hooks, subagents, and slash commands  
**Audience:** Beginner→intermediate Claude Code users who already saw CLAUDE.md, short codes, and RRR  
**Recommended slot:** 60-90 minutes, advanced afternoon block or ACC 2026 instructor-team module

## 1. Module thesis

Claude Code workshop should not stop at “write better prompts.” The advanced step is to teach students how to **compile repeated prompting into infrastructure**:

- `CLAUDE.md` for shared memory and lessons learned
- `SKILL.md` for reusable, on-demand workflows
- hooks for deterministic guardrails
- subagents for isolated specialist context
- tests as external truth

The important distinction from the Thai guide is:

> CLAUDE.md is advisory. Hooks are deterministic. Skills are reusable workflow packets loaded only when needed.

## 2. Success criteria

By the end, each participant should leave with:

1. One drafted project or personal skill with a trigger-tested `description`.
2. One hook design, ideally non-blocking first, with clear event/matcher/command.
3. A guardrail map deciding what belongs in CLAUDE.md vs skill vs hook vs subagent.
4. A verification habit: every workflow has a proof point before “done.”

## 3. Suggested timing options

### 60-minute slot

| Time | Segment | Output |
|---:|---|---|
| 0-8 | Mental model: CLAUDE.md vs Skill vs Hook vs Subagent | shared vocabulary |
| 8-25 | Skills anatomy + trigger accuracy | one SKILL.md draft |
| 25-40 | Hooks anatomy + safety ladder | one hook design |
| 40-52 | Live demo: migration-protection hook + release skill | visible deterministic guardrail |
| 52-60 | Debrief + homework | next action |

### 90-minute slot

| Time | Segment | Output |
|---:|---|---|
| 0-10 | Pain inventory: repeated prompts and repeated failures | candidate backlog |
| 10-30 | Skills: anatomy, description recipe, trigger tests | working skill draft |
| 30-45 | Skill peer review: trigger matrix | sharpened description |
| 45-60 | Hooks: events, matchers, blocking vs non-blocking | hook design card |
| 60-75 | Live implementation lab | `.claude/skills/...` + `.claude/hooks/...` |
| 75-85 | Compose with subagents/tests | operating-system map |
| 85-90 | RRR and next steps | learning captured |

## 4. Instructor story arc

1. **Start from pain:** “I used to prompt randomly and lose hours.”
2. **Introduce structure:** Plan Mode, lean CLAUDE.md, tests, worktrees, subagents.
3. **Reveal the missing layer:** Short codes are useful, but the reusable unit is the skill.
4. **Show deterministic guardrails:** Anything that must happen every time becomes a hook.
5. **Close with agency:** Students are not just using Claude Code; they are building their own AI operating system.

## 5. Required demo files

Create these inside a throwaway demo repo during class.

### `.claude/skills/release-checklist/SKILL.md`

```markdown
---
name: release-checklist
description: Release checklist for shipping a project. Use when user says "release", "ship this", "deploy prod", or wants to publish a version. Do NOT trigger for local dev server or preview-only deploys.
argument-hint: "[staging|production]"
---

# Release Checklist

## Outcome
A release is prepared with tests, risk notes, rollback plan, and a final evidence report.

## Required checks
- Read current git status and diff.
- Identify changed behavior.
- Run the smallest relevant tests first.
- Confirm rollback path.

## Steps
1. Summarize what is being released.
2. Run targeted tests.
3. Run broader validation if available.
4. Draft release notes.
5. Report Tested / Not-tested.

## Stop conditions
Stop and ask only for production credentials, irreversible deploys, or missing authority.
```

### `.claude/hooks/protect-migrations.py`

```python
#!/usr/bin/env python3
import json
import sys

payload = json.load(sys.stdin)
tool = payload.get("tool_name", "")
inputs = payload.get("tool_input", {})
paths = []
for key in ("file_path", "path"):
    if inputs.get(key):
        paths.append(str(inputs[key]))
for edit in inputs.get("edits", []) or []:
    if isinstance(edit, dict) and edit.get("file_path"):
        paths.append(str(edit["file_path"]))

if tool in {"Edit", "Write", "MultiEdit"} and any("/migrations/" in p for p in paths):
    print("Migration files are immutable. Create a new migration instead.", file=sys.stderr)
    print('{"decision":"block","reason":"Do not edit existing migration files."}')
```

### `.claude/settings.json` hook snippet

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Edit|Write|MultiEdit",
        "hooks": [
          {
            "type": "command",
            "command": "$CLAUDE_PROJECT_DIR/.claude/hooks/protect-migrations.py",
            "timeout": 10
          }
        ]
      }
    ]
  }
}
```

Do not enable this in the workshop repo itself unless the class is ready to debug hooks. Treat it as demo material.

## 6. Activity — Guardrail map

Ask learners to fill this table for their real project:

| Repeated pain | Best layer | Why |
|---|---|---|
| I repeat the same release steps | Skill | reusable workflow |
| AI edits generated files | Hook | deterministic block |
| AI forgets business rules | CLAUDE.md or skill | persistent context |
| Security review is too big | Subagent | isolated context |
| Done claims are weak | Tests + Stop hook | external truth |

Rule: implement only one guardrail first. Too many hooks at once creates friction.

## 7. Activity — Trigger matrix

For each skill, require at least 5 prompts:

| Prompt | Expected | Notes |
|---|---|---|
| “ship this to prod” | trigger | release intent |
| “start local server” | no trigger | collision with dev workflow |
| “make preview deployment” | no/clarify | not production |
| “rollback production” | trigger | release incident path |
| “write PR description” | no trigger | different skill |

If the team disagrees, edit `description`, not the body.

## 8. Instructor notes for advanced nuance

- Hooks should be fast. Slow hooks make agents less willing to act.
- Start non-blocking: log or warn before blocking.
- Blocking hooks need remediation text: tell Claude what to do next.
- Avoid network calls in every hook.
- Prefer project hook scripts via `$CLAUDE_PROJECT_DIR` so paths work from any cwd.
- Commit shared project hooks only when the whole team accepts the policy.
- Keep secrets out of CLAUDE.md, settings files, hook logs, and skill examples.
- Hooks are not a replacement for tests; they are guardrails around tool use.

## 9. Assessment rubric

| Level | Evidence |
|---|---|
| Pass | Has one SKILL.md with name + description + body |
| Good | Has trigger phrases and negative collisions |
| Strong | Has trigger matrix and peer-reviewed wording |
| Advanced | Pairs skill with hook and test evidence |
| Instructor-ready | Can explain why each rule belongs in CLAUDE.md, Skill, Hook, or Subagent |

## 10. Placement in existing SIIT workshop

Recommended insertion:

- after Short Codes, if teaching how short codes evolve into skills; or
- after RRR, if teaching how retrospectives generate new skills/hooks; or
- advanced optional block replacing/augmenting “Lessons Learned”.

For a full-day beginner class, use 60 minutes. For ACC 2026 instructor team or advanced class, use 90 minutes plus homework.

## 11. Homework

1. Convert one repeated prompt into a skill.
2. Write a trigger matrix with at least five prompts.
3. Design one hook but start in non-blocking mode.
4. Run RRR and add one lesson to CLAUDE.md only if it is broadly useful.

## 12. Source notes

- Thai Claude Code guide: Plan Mode, lean CLAUDE.md, hooks, worktrees, tests, subagents, skills, and SKILL.md creation.
- Anthropic hooks docs: hooks live in settings files; events include PreToolUse, PostToolUse, UserPromptSubmit, Stop, SubagentStop, Notification, PreCompact; matchers support exact strings, regex, `*`, and optional timeout.
- Anthropic subagents docs: project/user agents are Markdown files with `name`, `description`, optional `tools`; separate context; project agents override user agents.
- Anthropic slash commands docs: custom commands live in `.claude/commands/` or `~/.claude/commands/`, support frontmatter and arguments.


## 13. Companion artifacts

- `acc-2026-hooks-skills-proposal.md` — 3-hour instructor-team proposal and Thai chat-ready summary.
- `materials/hooks-skills/worksheets.md` — learner worksheets for pain inventory, skill design, trigger matrix, hook design, payload observation, and mini-deck creation.


## Rehearsal

Use `hooks-skills-rehearsal-checklist.md` before delivery to verify anchors, timing, demos, materials, and RRR capture.
