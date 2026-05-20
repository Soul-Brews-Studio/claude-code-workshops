# Hooks + Skills Worksheets

Print or copy these into the learner repo.

## Worksheet 1 — Pain inventory

List repeated prompts or repeated failures from your work.

| # | Pain / repeated phrase | What happens if missed? | Candidate layer |
|---:|---|---|---|
| 1 | | | CLAUDE.md / Skill / Hook / Subagent |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

Decision hints:

- repeated knowledge → CLAUDE.md
- repeated workflow → Skill
- must never happen → Hook
- context-heavy specialist work → Subagent
- correctness proof → Test

## Worksheet 2 — Skill design card

```text
Skill name:
Human job it replaces:
Who will use it:
Done means:
Inputs needed:
Verification evidence:
```

### Description draft

```text
<Purpose>. Use when user says "...", "...", or wants to .... Do NOT trigger for ... (use /...).
```

### Trigger matrix

| Prompt | Should trigger? | Why / edit needed |
|---|---|---|
| | yes / no / clarify | |
| | yes / no / clarify | |
| | yes / no / clarify | |
| | yes / no / clarify | |
| | yes / no / clarify | |

## Worksheet 3 — Hook design card

```text
Invariant to enforce:
Risk level: low / medium / high / critical
Hook event: PreToolUse / PostToolUse / UserPromptSubmit / Stop / SubagentStop / PreCompact
Matcher:
Command:
Timeout:
Should block? yes/no
Message Claude should see:
Human override path:
```

### Safety review

- [ ] Matcher is narrow.
- [ ] Command is fast.
- [ ] No secrets are logged.
- [ ] Failure message says what to do next.
- [ ] Hook starts as warn/log unless risk is high.
- [ ] Team agrees before committing shared policy.

## Worksheet 4 — Hook payload observation

Before writing a blocking hook, observe payload shape.

```python
#!/usr/bin/env python3
import json, sys
payload = json.load(sys.stdin)
print(json.dumps({
    "event": payload.get("hook_event_name"),
    "tool": payload.get("tool_name"),
    "tool_input_keys": sorted((payload.get("tool_input") or {}).keys()),
}, ensure_ascii=False), file=sys.stderr)
```

Questions:

1. Which fields are stable enough to rely on?
2. Which paths or commands should be checked?
3. What false positives might block good work?
4. What should Claude do when blocked?

## Worksheet 5 — Mini deck from a workflow

Turn your skill/hook into 5 teaching slides.

| Slide | Purpose | Content |
|---:|---|---|
| 1 | Pain story | |
| 2 | Mental model | |
| 3 | File format | |
| 4 | Bad vs good | |
| 5 | Exercise | |

Rule: every deck must include a live artifact, not only concepts.

## Exit ticket

Before leaving, write:

1. The one skill I will keep using is:
2. The one hook I will test in warn-only mode is:
3. The thing I will add to CLAUDE.md is:
4. The thing I will NOT automate yet is:


## Worksheet 8 — DNA card exercise

Use Boy's `boy-dna-demo/resonance_peng.md` as inspiration: a useful AI/domain persona is transparent about what it is made from.

```text
Persona / skill name:
Who this helps:
Domain:
Voice:
Masters / references / standards:
Local vocabulary:
Tasks it should handle:
Tasks it must refuse or hand off:
Evidence it should cite:
```

### Why this matters

A domain skill is not only instructions. It is a compact identity plus operating constraints. For accounting, legal, medical, or safety domains, learners must name sources and limits clearly.

