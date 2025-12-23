# Lessons Learned
## Meta Workshop - เรียนรู้จากการสร้าง Workshop

---

## The Loop

```
nnn → gogogo → rrr
```

| Code | Action | Result |
|------|--------|--------|
| `nnn` | วางแผน | GitHub Issue |
| `gogogo` | ลงมือทำ | Code + Commits |
| `rrr` | สรุป | Retrospective |

**Pattern**: Plan → Execute → Reflect → Repeat

---

## Short Codes in Action

วันนี้ใช้จริง:

```
nnn     → สร้าง issue #8 (plan slides)
gogogo  → สร้าง slides + PR
/trace  → หา context ข้าม repos
```

**ผลลัพธ์**:
- 6 issues created
- 3 PRs merged
- 34+ slides

---

## /trace - Parallel Agents

```markdown
# /trace [project-name]

Launch 5 subagents simultaneously:

1. Current Repo Files  → grep/find
2. Git History         → git log --grep
3. GitHub Issues       → gh issue list
4. Other Repos         → find ~/Code
5. Retrospectives      → grep ψ/memory/
```

**Power**: 5 agents = 5x faster search

---

## /trace Structure

```yaml
---
description: ตามรอย Project ที่หายไป
allowed-tools:
  - Bash
  - Grep
  - Glob
  - Task
---

# Step 0: Timestamp
date "+%H:%M (%A %d %B %Y)"

# Step 1-5: Launch parallel agents
```

**Key**: `allowed-tools` = security boundary

---

## GitHub Flow

```
Issue → Branch → Code → PR → Merge
```

| Step | Command |
|------|---------|
| 1. Issue | `gh issue create` |
| 2. Branch | `git checkout -b feat/xxx` |
| 3. Code | Edit files |
| 4. PR | `gh pr create` |
| 5. Merge | Review → Merge |

**ไม่ commit ตรงไป main**

---

## Content Iteration

```
v1 (27 slides) → "too detail!" → v2 (12 slides)
```

| Version | Slides | Feedback |
|---------|--------|----------|
| v1 | 27 | Too tight, too detail |
| v2 | 12 | Good! Overview style |

**Lesson**: Overview > Detail

---

## Deployment Made Simple

```jsonc
// wrangler.jsonc
{
  "name": "claude-code-workshops",
  "assets": {
    "directory": "./public"
  }
}
```

```bash
npx wrangler deploy
```

**No worker.js needed** for static sites

---

## Knowledge Organization

```
vault/
├── 00-MOC.md          # Map of Content
├── 1x-concepts/       # 10, 11, 12...
├── 2x-short-codes/    # 20, 21, 22...
├── 3x-workflows/      # 30, 31...
└── 4x-slides/         # 40, 41, 42...
```

**Pattern**: Numbered prefixes = ordering

---

## Anti-Patterns

| Don't | Do Instead |
|-------|------------|
| Detail first | Overview first, iterate |
| Commit to main | Branch → PR → Merge |
| Guess user wants | Ask, get feedback |
| Manual search | Use /trace parallel agents |
| Single source | Multi-remote git |

---

## Create Your Own /command

```markdown
---
description: Your command description
allowed-tools:
  - Bash
  - Task
---

# /your-command

## Step 1: Do something
...

## Step 2: Launch agents
subagent_type: context-finder
prompt: |
  Your prompt here
```

Save to: `.claude/commands/your-command.md`

---

## Key Takeaways

1. **Loop**: `nnn → gogogo → rrr` = structured work
2. **Parallel**: 5 agents searching = fast results
3. **Iterate**: v1 → feedback → v2 = better output

```
Plan before doing.
Search in parallel.
Learn from feedback.
```
