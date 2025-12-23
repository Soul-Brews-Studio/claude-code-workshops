# Collaborate with AI to Create/Improve CLAUDE.md

> **Teaching Slide**: How to work with Claude to build your CLAUDE.md

---

## SLIDE 1: You Don't Write CLAUDE.md Alone 🤝

**The Secret**: Let Claude help you write CLAUDE.md!

**Traditional Approach** ❌:
1. Read documentation
2. Figure out structure
3. Write everything manually
4. Hope it's correct

**AI-Powered Approach** ✅:
1. Talk to Claude about your project
2. Claude drafts CLAUDE.md
3. You review and refine
4. Iterate together

**Result**: Better CLAUDE.md in less time

---

## SLIDE 2: Starting from Scratch 🌱

**Conversation Example**:

```
You: "I want to create a CLAUDE.md for my project.
     It's a Next.js e-commerce site with PostgreSQL.
     We use pnpm and deploy on Vercel.
     Team of 3 developers."

Claude: "I'll create a CLAUDE.md for you! Let me ask
        a few questions first:
        - What are your critical safety rules?
        - Do you have any specific workflows?
        - What should I never do?
        - What tools do you prefer?"

You: "Never force push. Always create PRs.
     Use pnpm, not npm. Test on Safari."

Claude: "Here's your CLAUDE.md..."
        [Creates complete document]
```

**Time**: 5-10 minutes vs hours of manual writing

---

## SLIDE 3: The Conversation Pattern 💬

**How to talk to Claude**:

### 1. Project Context
```
"My project is..."
- What: E-commerce platform
- Stack: Next.js, PostgreSQL, Tailwind
- Team: 3 devs
- Tools: pnpm, Vercel, GitHub Actions
```

### 2. Safety Rules
```
"Never do this..."
- No force push
- No direct push to main
- No merging own PRs
- Must test on Safari
```

### 3. Workflows
```
"Our process is..."
- Issue on Linear
- Branch from main
- 2 PR approvals needed
- Deploy staging first
```

### 4. Preferences
```
"We prefer..."
- pnpm over npm
- Tailwind over CSS
- Supabase for DB
- TypeScript strict mode
```

**Claude creates**: Complete CLAUDE.md based on this conversation

---

## SLIDE 4: Improving Existing CLAUDE.md 🔧

**You already have CLAUDE.md? Ask Claude to improve it!**

**Conversation Example**:

```
You: "Read my CLAUDE.md and suggest improvements.
     Focus on making it clearer and adding
     missing safety rules."

Claude: [Reads file]
        "Here are 5 improvements I suggest:
        1. Add short codes section (rrr, nnn, lll)
        2. Clarify git workflow (missing PR template)
        3. Add retrospective template
        4. Specify test requirements
        5. Add common mistakes section

        Should I make these changes?"

You: "Yes, add short codes and test requirements."

Claude: [Updates CLAUDE.md with only requested changes]
```

**Benefit**: Incremental improvement, not full rewrite

---

## SLIDE 5: The Iterative Process 🔄

**CLAUDE.md grows with your project**

```
Week 1: Basic structure
├── Project overview
├── Safety rules
└── Quick start

Week 2: Add workflows
└── + Development flow
    + Testing process

Week 3: Add learnings
└── + Lessons learned
    + Common mistakes

Week 4: Add short codes
└── + rrr (retrospective)
    + nnn (planning)
```

**Pattern**: Start simple → Add as you learn

**How Claude helps**:
- "Add lesson learned about X to CLAUDE.md"
- "Update workflow with new step Y"
- "Create short code for Z"

---

## SLIDE 6: Live Example - Creating CLAUDE.md 🎬

**Let's create one together! (Live Demo)**

### Step 1: Open Claude
```
You: "Help me create a CLAUDE.md for my project"
```

### Step 2: Answer Questions
```
Claude: "What's your project?"
You:    "Blog platform with Next.js"

Claude: "What tools?"
You:    "pnpm, Vercel, PostgreSQL"

Claude: "Any safety rules?"
You:    "No force push, test before deploy"
```

### Step 3: Review Draft
```
Claude: [Shows CLAUDE.md draft]
        "Here's your CLAUDE.md.
        Does this look good?"
```

### Step 4: Refine
```
You: "Add a section about our design system"
Claude: [Updates CLAUDE.md]
```

### Step 5: Save
```
You: "Perfect! Save it."
Claude: [Saves CLAUDE.md to your repo]
```

**Total time**: 5 minutes ⚡

---

## SLIDE 7: Specific Revision Requests 🎯

**Ask Claude for specific changes**:

### Add Safety Rule
```
You: "Add a rule: Never commit .env files"
Claude: [Updates Safety Rules section]
```

### Add Workflow
```
You: "Add our PR review process:
     1. Create PR
     2. Request 2 reviews
     3. Wait for CI
     4. Merge after approval"
Claude: [Adds to Workflows section]
```

### Add Short Code
```
You: "Create short code 'deploy' that:
     - Runs tests
     - Builds project
     - Deploys to Vercel"
Claude: [Adds to Short Codes section with details]
```

### Update Project Info
```
You: "We switched from npm to pnpm"
Claude: [Updates all npm references to pnpm]
```

---

## SLIDE 8: Common Questions to Ask Claude 💭

**When creating/updating CLAUDE.md**:

1. **"What am I missing in my CLAUDE.md?"**
   - Claude analyzes and suggests additions

2. **"Is this safety rule clear enough?"**
   - Claude reviews and improves clarity

3. **"Can you add examples to this section?"**
   - Claude adds practical examples

4. **"Reorganize this for better readability"**
   - Claude restructures content

5. **"What would other teams add here?"**
   - Claude suggests industry best practices

6. **"Make this section more concise"**
   - Claude simplifies without losing info

7. **"Add a quick reference card"**
   - Claude creates printable summary

---

## SLIDE 9: Template-Based Creation 📋

**Use the generic template as starting point**:

```
You: "Use this template to create my CLAUDE.md:
     [paste generic template URL]

     Customize it for:
     - Project: Analytics dashboard
     - Stack: React, Node.js, MongoDB
     - Team: 5 developers
     - Tools: Yarn, Docker, Jenkins"

Claude: [Takes template]
        [Customizes all sections]
        [Adds project-specific details]
        "Here's your customized CLAUDE.md"
```

**Benefit**: Professional structure + your specifics

---

## SLIDE 10: Maintenance Conversations 🔧

**Keep CLAUDE.md updated**:

### After Learning Something
```
You: "We learned: Always check Safari before deploy.
     Add this to lessons learned section."
Claude: [Updates Lessons Learned]
```

### When Process Changes
```
You: "We now use GitHub Actions instead of Jenkins.
     Update the CI/CD section."
Claude: [Updates entire CI/CD workflow]
```

### When Adding Tool
```
You: "We added Playwright for E2E testing.
     Add to tools section and testing workflow."
Claude: [Updates Tools + Workflows sections]
```

### When Finding Mistake
```
You: "Remove the section about npm. We don't use it."
Claude: [Removes all npm references]
```

---

## SLIDE 11: Quality Check Conversation ✅

**Ask Claude to review quality**:

```
You: "Review my CLAUDE.md and check:
     - Is it clear?
     - Any missing safety rules?
     - Are examples helpful?
     - Is structure logical?"

Claude: [Analyzes]
        "Quality check results:
        ✅ Clear and well-structured
        ⚠️  Missing: Database backup safety rule
        ⚠️  Missing: API rate limit handling
        ✅ Examples are practical
        💡 Suggestion: Add troubleshooting section

        Should I add the missing items?"

You: "Yes, add them"
Claude: [Updates CLAUDE.md]
```

**Benefit**: Expert review + instant fixes

---

## SLIDE 12: Collaborative Best Practices 🌟

**How to work effectively with Claude on CLAUDE.md**:

### DO ✅
- Be specific: "Add X to section Y"
- Ask questions: "What's missing?"
- Request reviews: "Is this clear?"
- Iterate: Start simple, improve over time
- Save versions: Commit after each improvement

### DON'T ❌
- Be vague: "Make it better"
- Accept blindly: Review Claude's suggestions
- Overload: Don't ask for everything at once
- Forget updates: Keep it current
- Skip review: Always check before saving

### BEST PRACTICE
```
1. Start with basics (15 min)
2. Use for 1 week
3. Ask Claude: "What problems do you see?"
4. Update based on real experience
5. Repeat monthly
```

---

## SLIDE 13: Real Conversation Examples 💬

### Example 1: First Creation
```
👤 You: "Create CLAUDE.md for blog platform"
🤖 Claude: "I'll need some details..."
👤 You: "Next.js, pnpm, Vercel, 2 devs"
🤖 Claude: [Creates complete CLAUDE.md]
👤 You: "Add no force push rule"
🤖 Claude: [Updates safety section]
✅ Done: 5 minutes
```

### Example 2: Adding Learnings
```
👤 You: "Add lesson: Safari has different date handling"
🤖 Claude: [Adds to Lessons Learned with example]
✅ Done: 30 seconds
```

### Example 3: Workflow Update
```
👤 You: "Update PR workflow to require 2 reviews"
🤖 Claude: [Updates workflow section]
🤖 Claude: "Should I update the git commit template too?"
👤 You: "Yes"
🤖 Claude: [Updates both sections]
✅ Done: 1 minute
```

### Example 4: Quality Review
```
👤 You: "Review my CLAUDE.md for improvements"
🤖 Claude: [Lists 3 suggestions with reasoning]
👤 You: "Implement #1 and #3"
🤖 Claude: [Makes selected improvements]
✅ Done: 2 minutes
```

---

## SLIDE 14: Workshop Exercise 🎯

**Let's practice together!**

### Task (10 minutes)
1. Open Claude
2. Say: "Help me create a CLAUDE.md"
3. Answer Claude's questions
4. Review the draft
5. Ask for 1 improvement
6. Save to your project

### What You'll Learn
- How to describe your project to Claude
- How to request specific changes
- How to review AI-generated content
- How to iterate effectively

### Success Criteria
✅ You have a working CLAUDE.md
✅ It has safety rules
✅ It has your project info
✅ You made at least 1 improvement
✅ It's saved in your repo

---

## SLIDE 15: Key Takeaways 🎓

### 1. **Claude is Your Co-Author**
- Don't write alone
- Describe what you need
- Let Claude draft
- You review and refine

### 2. **Start Simple, Iterate**
- Basic version: 5 minutes
- Improve over time
- Add learnings as you go

### 3. **Be Specific in Requests**
- "Add X to section Y"
- "Update Z with new info"
- "Review for improvements"

### 4. **Keep It Current**
- Update after process changes
- Add lessons learned
- Remove outdated info

### 5. **Quality Over Perfection**
- Working CLAUDE.md today > perfect one never
- Improve gradually
- Real usage reveals what's needed

---

## Summary Card (Print-Friendly) 📇

```
╔═══════════════════════════════════════════╗
║   COLLABORATE WITH AI ON CLAUDE.MD        ║
╠═══════════════════════════════════════════╣
║ Creating from Scratch:                    ║
║  1. "Help me create a CLAUDE.md"          ║
║  2. Answer Claude's questions             ║
║  3. Review draft                          ║
║  4. Request refinements                   ║
║  5. Save to repo                          ║
║                                           ║
║ Improving Existing:                       ║
║  • "Add [X] to section [Y]"               ║
║  • "Review my CLAUDE.md"                  ║
║  • "Update [Z] with new info"             ║
║  • "Make [section] clearer"               ║
║                                           ║
║ Maintenance:                              ║
║  • Add lessons: "We learned [X]"          ║
║  • Update tools: "We now use [Y]"         ║
║  • Quality check: "Review and improve"    ║
║                                           ║
║ Best Practice:                            ║
║  Start simple → Use 1 week → Review →     ║
║  → Update → Repeat monthly                ║
╚═══════════════════════════════════════════╝
```

**Remember**: CLAUDE.md is living document. Claude helps it grow with your project! 🌱
