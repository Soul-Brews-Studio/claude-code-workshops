---
name: ccc
description: Create context issue and compact conversation. Use when user says "ccc", "save context", "context dump", or before switching tasks.
allowed-tools:
  - Bash
  - Read
  - Write
  - Glob
  - Grep
---

# /ccc - Create Context & Compact

Save session state to GitHub issue, then compact conversation.

## Usage

```
/ccc                    # Save context to GitHub issue
/ccc --local            # Save to local file only (no GitHub)
```

## Step 0: Timestamp

```bash
date "+🕐 %H:%M (%A %d %B %Y)"
```

## Step 1: Gather Information

Run in parallel:

```bash
# Git status
git status --porcelain

# Recent commits
git log --oneline -5

# Current branch
git branch --show-current

# Changed files summary
git diff --stat HEAD~3 2>/dev/null || echo "Less than 3 commits"
```

## Step 2: Analyze Session Context

Review conversation for:
- Current task/goal
- Key discoveries made
- Files modified/created
- Decisions made
- Blockers encountered
- Next steps identified

## Step 3: Create Context Issue

```bash
gh issue create --title "ctx: [Brief description of current state]" --body "$(cat <<'EOF'
## Session Context

**Date**: [YYYY-MM-DD HH:MM GMT+7]
**Branch**: [current-branch]
**Working On**: [Brief description]

## Current State

### What We're Doing
[1-2 sentences about the current task]

### Progress
- [x] Completed item 1
- [x] Completed item 2
- [ ] In progress: item 3
- [ ] Next: item 4

## Key Discoveries

- Discovery 1: [What was learned]
- Discovery 2: [Important finding]

## Changed Files

```
[git status output]
```

## Decisions Made

| Decision | Rationale |
|----------|-----------|
| [Choice] | [Why] |

## Blockers / Issues

- [Any blockers encountered]

## Next Steps

1. [ ] Immediate next action
2. [ ] Follow-up task
3. [ ] Future consideration

## Notes for Next Session

[Any important context for resuming work]

---
*Context saved via /ccc*
EOF
)"
```

## Step 4: Compact Conversation

After creating the issue, tell the user:

```
Context saved to issue #[number].
Run /compact to reduce conversation length.
```

## --local Mode

If `--local` flag, save to file instead:

**Location**: `ψ/memory/contexts/YYYY-MM-DD_HH-MM_context.md`

```bash
mkdir -p ψ/memory/contexts
cat > "ψ/memory/contexts/$(date +%Y-%m-%d_%H-%M)_context.md" << 'EOF'
[Same template as above]
EOF
```

## Output

```markdown
## Context Saved

**Issue**: #[number] (or local file path)
**Branch**: [branch-name]
**Summary**: [1-line summary]

### Quick Stats
- Files changed: [N]
- Commits since main: [N]
- Session duration: ~[X] minutes

💡 Run `/compact` to reduce conversation length
```

---

ARGUMENTS: $ARGUMENTS
