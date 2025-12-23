---
type: slides
target: gemini | canvas | gamma
status: draft
created: 2025-12-23
topic: SIIT Fullday Workshop - GitHub CLI (Part 2)
audience: SIIT students, intermediate developers
duration: 1.5 hours
style: technical, hands-on
---

# GitHub CLI for Agentic Workflows
## Part 2: gh CLI

---

## SLIDES CONTENT

### SLIDE 1: Title
```
Title: GitHub CLI for Agentic Workflows
Subtitle: gh CLI + AI = fast, auditable work
Part 2: GitHub CLI
```

---

### SLIDE 2: Why gh CLI
```
Title: Why CLI Instead of UI
- Scriptable and repeatable
- Perfect for AI collaboration
- Works in any terminal
- Keeps history and traceability
```

---

### SLIDE 3: Install gh CLI
```
Title: Install GitHub CLI
- macOS: brew install gh
- Windows: winget install GitHub.cli
- Linux: apt/yum (see docs)
Verify: gh --version
```

---

### SLIDE 4: Authenticate
```
Title: Login
Command:
- gh auth login
Tip: Choose HTTPS + browser auth
```

---

### SLIDE 5: Verify Auth
```
Title: Check Status + Scopes
Command:
- gh auth status
Ensure scopes: repo, read:org
Thai: ถ้าไม่มีสิทธิ์ ให้ login ใหม่
```

---

### SLIDE 6: Create Repo (Local)
```
Title: Create Repo from Current Folder
Command:
- gh repo create --source .
Options: public | private
Result: remote added + pushed
```

---

### SLIDE 7: Create Repo in Org
```
Title: Create in Workshop Org
Command:
- gh repo create org-name/repo-name --private --source .
Example org: Workshop-Agentic-AI
```

---

### SLIDE 8: First Commit
```
Title: README + First Push
Commands:
- echo "# My Agent" > README.md
- git add README.md
- git commit -m "init"
- git push
```

---

### SLIDE 9: Issues 101
```
Title: Issues = Task Memory
Why issues:
- Track context + plans
- Share with AI and humans
- Acts as a time capsule
Command: gh issue create
```

---

### SLIDE 10: Context Issue (ccc)
```
Title: Issue Template: Context
Fields:
- Summary of current state
- Changed files
- Decisions made
- Next steps
Used by short code: ccc
```

---

### SLIDE 11: Plan Issue (nnn)
```
Title: Issue Template: Plan
Fields:
- Problem statement
- Options + tradeoffs
- Steps to execute
- Risks + tests
Used by short code: nnn
```

---

### SLIDE 12: Labels + Milestones
```
Title: Organize Work
Commands:
- gh label create "plan" --color 0E8A16
- gh label create "context" --color BFD4F2
- gh milestone create "Workshop"
```

---

### SLIDE 13: List Issues
```
Title: Find What Matters
Commands:
- gh issue list
- gh issue list --label plan
- gh issue list --author @me
```

---

### SLIDE 14: View + Comment
```
Title: Review and Update
Commands:
- gh issue view 12
- gh issue comment 12 --body "update"
- gh issue close 12
```

---

### SLIDE 15: Pull Requests
```
Title: Create PR from CLI
Commands:
- gh pr create --fill
- gh pr view
- gh pr status
```

---

### SLIDE 16: Review Flow
```
Title: Safe Merge Flow
- Create PR
- Human review
- Merge after approval
Rule: AI never merges to main
```

---

### SLIDE 17: Sync + Clean
```
Title: Keep Branches Fresh
Commands:
- gh repo sync
- git fetch --all
- gh pr checkout 15
```

---

### SLIDE 18: gh api (Optional)
```
Title: Advanced Automation
Command:
- gh api repos/:owner/:repo/issues
Use cases:
- Batch labeling
- Metrics and reports
```

---

### SLIDE 19: AI Prompt Example
```
Title: Ask Claude to Use gh
Prompt:
"We have gh CLI. Create a private repo in org X, add README, push, then open a plan issue."
Outcome: reproducible, auditable setup
```

---

### SLIDE 20: Exercise + Transition
```
Title: Hands-On + Next Module
Exercise:
- Create repo
- Open one context issue
- Open one plan issue
Next: Build your CLAUDE.md
```
