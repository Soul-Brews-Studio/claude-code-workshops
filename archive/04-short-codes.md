---
type: slides
target: gemini | canvas | gamma
status: draft
created: 2025-12-23
topic: SIIT Fullday Workshop - Short Codes (Part 4)
audience: SIIT students, intermediate developers
duration: 1.5 hours
style: technical, hands-on
---

# Short Codes = Fast Collaboration
## Part 4: Short Codes

---

## SLIDES CONTENT

### SLIDE 1: Title
```
Title: Short Codes = Fast Collaboration
Subtitle: One word -> full workflow
Part 4: Short Codes
```

---

### SLIDE 2: Why Short Codes
```
Title: The Speed Advantage
- Short, repeatable prompts
- Consistent behavior across sessions
- Reduce prompt fatigue
- Easy for teams to share
```

---

### SLIDE 3: Where to Define
```
Title: Add to CLAUDE.md
Section: "Short Codes"
Format:
- code -> meaning
- when to use
- required inputs
```

---

### SLIDE 4: Core Set
```
Title: The 5 Core Codes
- lll: status check
- ccc: capture context
- nnn: create plan
- gogogo: execute plan
- rrr: retrospective
```

---

### SLIDE 5: lll (Status)
```
Title: lll = Project Status
Output:
- current branch
- changed files
- open issues
- next recommended step
Use at the start of a session
```

---

### SLIDE 6: ccc (Context)
```
Title: ccc = Context Capture
Creates a context issue:
- summary of work
- decisions made
- files touched
- next steps
```

---

### SLIDE 7: nnn (Plan)
```
Title: nnn = Planning Issue
Creates a plan issue:
- problem statement
- options + tradeoffs
- step-by-step plan
- tests and risks
```

---

### SLIDE 8: gogogo (Execute)
```
Title: gogogo = Execute Plan
- Follows the approved plan
- Makes code changes
- Reports progress
- Stops if blocked
```

---

### SLIDE 9: rrr (Retro)
```
Title: rrr = Retrospective
- What happened
- What worked
- What failed
- Lessons learned
Used at end of session
```

---

### SLIDE 10: Two-Issue Pattern
```
Title: ccc -> nnn
Why two issues:
- Context = what happened
- Plan = what to do
Keeps history clean
```

---

### SLIDE 11: Full Loop
```
Title: The Full Cycle
ccc -> nnn -> gogogo -> rrr
This builds a learning system
Every cycle improves CLAUDE.md
```

---

### SLIDE 12: Example ccc Output
```
Title: Example Context Issue
- Summary: Added auth endpoint
- Files: src/auth.ts, routes.ts
- Decisions: JWT expiry 15m
- Next: add tests
```

---

### SLIDE 13: Example nnn Output
```
Title: Example Plan Issue
- Goal: add rate limiting
- Option A: middleware
- Option B: API gateway
- Steps: 1) add lib 2) wire 3) test
```

---

### SLIDE 14: Example gogogo Output
```
Title: Example Execution Log
- Step 1 done: installed package
- Step 2 done: wired middleware
- Step 3 pending: add tests
Asks for review before pushing
```

---

### SLIDE 15: Example rrr Output
```
Title: Example Retro
- Win: middleware integration easy
- Issue: missing load tests
- Lesson: add perf checklist
- Next: update CLAUDE.md rules
```

---

### SLIDE 16: Custom Short Codes
```
Title: Create Your Own
Examples:
- deploy: release checklist
- docs: update README
- demo: create demo script
Make them team-specific
```

---

### SLIDE 17: Naming + Arguments
```
Title: Design Rules
- Keep 3-5 letters
- Distinct sound
- Support args when needed
Example: "fix login" -> /fix login
```

---

### SLIDE 18: Avoid Misuse
```
Title: Common Pitfalls
- Too many codes
- Overlapping meanings
- Vague outputs
- No documentation in CLAUDE.md
```

---

### SLIDE 19: Exercise
```
Title: Define 3 Short Codes
Write:
1) code
2) when to use
3) expected output
Share with a partner
```

---

### SLIDE 20: Transition
```
Title: Next Up: Retrospectives
Why retrospectives turn work into long-term learning
```
