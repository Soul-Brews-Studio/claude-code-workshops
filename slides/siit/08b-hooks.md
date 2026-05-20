---
title: 08b Hooks
description: 60-90 minute Hooks lab variant
---

# 08b — Hooks
<!-- .slide: id="part-b-hooks" -->
## Deterministic Claude Code Guardrails

---

## Learning Outcomes

By the end, learners can:

1. Explain why hooks differ from CLAUDE.md.
2. Pick the correct hook event and matcher.
3. Design a safe warn-only or blocking hook.
4. Write a remediation message Claude can act on.

---

## CLAUDE.md vs Hook

| CLAUDE.md | Hook |
|---|---|
| advisory | deterministic |
| “please format” | runs formatter |
| “don’t edit migrations” | blocks edit |
| “remember tests” | stop gate can require evidence |

Rule: if missing it is costly, consider a hook.

---

## Hook Config Shape

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

---

## Core Events

| Event | Use |
|---|---|
| `PreToolUse` | block before risky tool |
| `PostToolUse` | format/log after successful tool |
| `UserPromptSubmit` | route/inject/block prompt |
| `Stop` | require final evidence |
| `SubagentStop` | require worker report |
| `PreCompact` | checkpoint before compaction |

---

## Matchers

For `PreToolUse` / `PostToolUse`:

```json
"matcher": "Edit|Write|MultiEdit"
```

- exact: `Write`
- regex: `Edit|Write`
- wildcard: `*`
- omit matcher for `Stop` / `UserPromptSubmit`

---

## Hook Payload Observation

Start by logging shape, not blocking.

```python
#!/usr/bin/env python3
import json, sys
payload = json.load(sys.stdin)
print(json.dumps({
  "event": payload.get("hook_event_name"),
  "tool": payload.get("tool_name"),
  "input_keys": sorted((payload.get("tool_input") or {}).keys()),
}), file=sys.stderr)
```

---

## Example — Protect Migrations

```python
#!/usr/bin/env python3
import json, sys
payload = json.load(sys.stdin)
inputs = payload.get("tool_input", {})
path = str(inputs.get("file_path", ""))
if "/migrations/" in path:
    print("Migration files are immutable. Create a new migration.", file=sys.stderr)
    print('{"decision":"block","reason":"Do not edit existing migration files."}')
```

---

## Example — Format After Edit

```bash
#!/usr/bin/env bash
set -euo pipefail
if command -v prettier >/dev/null 2>&1; then
  prettier --write . >/dev/null
fi
```

Use as `PostToolUse`. Keep it fast.

---

## Stop Gate Pattern

Use only for high-value completion checks.

```text
Stop hook checks:
- test evidence exists, OR
- final report includes Not-tested + reason
```

Blocking Stop without clear remediation creates frustration.

---

## Safety Ladder

| Risk | Hook behavior |
|---|---|
| low | log |
| medium | warn |
| high | block with remediation |
| critical | block + human approval path |

Start warn-only unless the risk is obvious.

---

## Hook Design Card

```text
Invariant:
Event:
Matcher:
Command:
Timeout:
Block? yes/no
Message Claude sees:
Human override path:
False positive risk:
```

---

## Skill + Hook Pairing

| Skill | Hook |
|---|---|
| release checklist | Stop gate for tests |
| db migration playbook | block editing old migrations |
| slide writer | markdown/link check |
| security review | secret-leak precheck |

Skill teaches workflow. Hook enforces invariant.

---

## Anti-Patterns

- full test suite after every edit
- broad wildcard matchers for everything
- network calls in hooks
- vague block messages
- logging secrets
- shared project hooks without team agreement

---

## Lab Exit

Show:

1. hook design card
2. warn-only payload observation output
3. one safe blocking condition OR why you chose not to block
4. remediation message

---

## Homework

Run the hook for 3 sessions in warn-only mode before making it blocking.
