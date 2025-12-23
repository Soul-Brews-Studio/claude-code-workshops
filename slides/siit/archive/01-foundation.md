---
type: slides
target: gemini | canvas | gamma
status: draft
created: 2025-12-23
topic: SIIT Fullday Workshop - Agentic AI & Claude Code (Part 1 Foundation)
audience: SIIT students, intermediate developers
duration: 2 hours
style: technical, hands-on
---

# Agentic AI & Claude Code
## Part 1: Foundation

---

## SLIDES CONTENT

### SLIDE 1: Title
```
Title: Agentic AI & Claude Code
Subtitle: Teach AI to Think Like You
Part 1: Foundation
Event: SIIT Fullday Workshop (Dec 26, 2025)
Speaker: Nat Weerawan
```

---

### SLIDE 2: Full-Day Map
```
Title: 5 Parts, 1 Workflow
- Part 1: Foundation
- Part 2: GitHub CLI
- Part 3: CLAUDE.md
- Part 4: Short Codes
- Part 5: Retrospectives
Goal: Build a personal AI workflow end-to-end
```

---

### SLIDE 3: Workshop Outcomes
```
Title: What You Will Leave With
- A working Claude Code setup
- A personal CLAUDE.md (AI DNA)
- A GitHub workflow with gh CLI
- Short codes for fast collaboration
- A learning loop with retrospectives
Thai: ได้ AI ที่รู้จักคุณและทำงานแทนคุณได้จริง
```

---

### SLIDE 4: The Problem
```
Title: Generic AI Feels Generic
- ต้องอธิบายใหม่ทุกครั้ง
- ไม่รู้บริบทงานของคุณ
- ตอบแบบกลางๆ ไม่ตรง style
- เสียเวลา prompt engineering ซ้ำๆ
```

---

### SLIDE 5: The Shift
```
Title: From AI Chat to Agentic AI
Definition: AI that acts with context, rules, and goals
- Reads your project
- Follows your workflow
- Executes multi-step tasks
- Learns from feedback
```

---

### SLIDE 6: AI Agent vs Agentic AI
```
Title: The Difference
AI Agent:
- Single task
- Stateless
- You micromanage
Agentic AI:
- Multi-step
- Memory + context
- You delegate outcomes
```

---

### SLIDE 7: Human in the Loop
```
Title: You Stay in Control
- AI proposes, human decides
- Ask before risky actions
- Review diffs and commands
- Safety is a workflow, not a feature
```

---

### SLIDE 8: Why Claude Code
```
Title: Claude Code = AI in Your Terminal
- Reads and edits files
- Runs commands
- Understands the repo
- Works with your tools (git, gh, npm)
```

---

### SLIDE 9: Terminal is the Control Room
```
Title: Why CLI Matters
- Reproducible steps
- Audit trail
- Works on any project
- Easy to automate with AI
```

---

### SLIDE 10: Prerequisites
```
Title: Setup Checklist
- Node.js 18+
- Git
- GitHub account
- Claude Code CLI
- gh CLI (GitHub CLI)
Optional: VS Code
```

---

### SLIDE 11: Install Claude Code
```
Title: Install + Start
Commands:
- npm install -g @anthropic-ai/claude-code
- cd your-project
- claude
Thai: เปิด CLI แล้วทักทายได้เลย
```

---

### SLIDE 12: Safety Defaults
```
Title: Safety Rules (Non-Negotiable)
- Never force push
- Never delete without confirmation
- Never merge to main without review
- Always show plan before execution
```

---

### SLIDE 13: The Context Triangle
```
Title: 3 Sources of Truth
1) Files (code + docs)
2) Terminal (commands + history)
3) Instructions (CLAUDE.md)
Good answers require all 3
```

---

### SLIDE 14: Context Budgeting
```
Title: Less Noise, More Signal
- Give only relevant files
- Summarize long docs
- Use file paths, not full dumps
- Ask AI what it needs next
```

---

### SLIDE 15: The Core Workflow (Preview)
```
Title: ccc -> nnn -> gogogo -> rrr
- ccc: capture context
- nnn: plan the work
- gogogo: execute plan
- rrr: retrospective
This is the learning loop
```

---

### SLIDE 16: Parallel Thinking (Preview)
```
Title: Multi-Agent Mindset
- Split tasks into focused agents
- Faster research + coding
- Reduce context overload
Preview for later modules
```

---

### SLIDE 17: Distillation Loop
```
Title: From Experience to System
- Raw session notes
- Retrospective summaries
- Update CLAUDE.md rules
- Workflow gets smarter over time
```

---

### SLIDE 18: Hands-On 1 (Research)
```
Title: Prepare Context
Task: Research yourself or a topic
- Use Gemini / Claude / web
- 10 key facts only
Thai: สรุปแบบ bullet สั้นๆ
```

---

### SLIDE 19: Hands-On 2 (Workspace)
```
Title: Create Your Project Folder
Commands:
- mkdir 01-my-agent
- cd 01-my-agent
Check:
- pwd
```

---

### SLIDE 20: Hands-On 3 (Start Claude)
```
Title: First Launch
Commands:
- claude
Inside Claude:
- pwd
- ls
Goal: Verify the agent sees your folder
```

---

### SLIDE 21: Hands-On 4 (First Prompt)
```
Title: First Prompt
Prompt:
"Explain this folder structure and suggest next steps"
Goal: Let AI read context and respond clearly
```

---

### SLIDE 22: Hands-On 5 (Define You)
```
Title: Define Your Style
Write 3 bullets:
- WHO: who you are
- HOW: preferred response style
- RULES: must ask before doing
Thai: เขียนแบบสั้นๆ ใช้งานจริง
```

---

### SLIDE 23: Common Pitfalls
```
Title: Avoid These
- Assumption escalation
- Too much context
- Vague instructions
- Skipping verification under time pressure
```

---

### SLIDE 24: Checkpoint
```
Title: Quick Review
- Claude Code installed
- Workspace ready
- First prompt done
- Personal preferences drafted
Q&A
```

---

### SLIDE 25: Transition
```
Title: Next Up: GitHub CLI
Why: Turn workflows into trackable issues
We will create repos, issues, and PRs with AI
```
