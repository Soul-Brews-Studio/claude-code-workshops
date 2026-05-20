# Hooks + Skills Lab Materials

Use these as copy/paste handouts during the advanced module.

## Lab order

1. Create `release-checklist` skill.
2. Write trigger matrix before testing.
3. Add a non-blocking hook design.
4. Convert it to a blocking hook only after the class understands the risk.
5. Close with RRR: what should become a skill next?

## Skill starter

```markdown
---
name: release-checklist
description: Release checklist for shipping a project. Use when user says "release", "ship this", "deploy prod", or wants to publish a version. Do NOT trigger for local dev server or preview-only deploys.
argument-hint: "[staging|production]"
---

# Release Checklist

## Outcome

## Inputs

## Steps

## Verification

## Final Report
```

## Hook starter

```python
#!/usr/bin/env python3
import json, sys
payload = json.load(sys.stdin)
print("hook saw event for", payload.get("tool_name", "unknown"), file=sys.stderr)
```

Start by observing. Block only after learners see the event payload and can explain the rule.

## Worksheets

Use `worksheets.md` for learner-facing exercises: pain inventory, skill design, hook design, payload observation, mini deck, and exit ticket.
