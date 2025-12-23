---
title: CLAUDE.md Deep Dive
description: Part 3 of SIIT Workshop - 25 slides
---

# CLAUDE.md Deep Dive
## สอน AI ให้รู้จักคุณ

---

<!-- 3.1 Why CLAUDE.md? -->

## ปัญหา: AI ไม่รู้จัก Context

- AI เริ่มใหม่ทุกครั้ง = **ไม่จำอะไรเลย**
- ต้องอธิบายซ้ำ: "project นี้ใช้ Next.js..."
- AI ทำผิด style, ผิด pattern ของ project
- เสียเวลา context switching ทุกครั้ง

---

## Solution: CLAUDE.md = DNA ของ Project

- ไฟล์ markdown ที่ **AI อ่านก่อนทุกครั้ง**
- บอก AI ว่า: คุณคือใคร, project คืออะไร, rules คืออะไร
- เหมือน **onboarding doc** สำหรับ AI
- Version control ได้ = track การเปลี่ยนแปลง

---

## Before vs After

| Before | After |
|--------|-------|
| อธิบายซ้ำทุกครั้ง | บอกครั้งเดียว |
| AI ทำผิด style | Consistent output |
| ลืม context | Always remembered |
| ไม่ shareable | Team ใช้ร่วมกันได้ |

---

<!-- 3.2 Structure Overview -->

## CLAUDE.md มี 12 Sections

```
1. Executive Summary      7. Context Management
2. Quick Start Guide      8. Technical Reference
3. Project Context        9. Development Practices
4. Critical Safety Rules  10. Lessons Learned
5. Development Environment 11. Troubleshooting
6. Development Workflows  12. Appendices
```

---

## MUST vs OPTIONAL

### 🔴 MUST HAVE
- **Project Context** — AI ต้องรู้ว่า project คืออะไร
- **Safety Rules** — ป้องกัน AI ทำพัง
- **Short Codes** — workflow ของคุณ

### 🟡 NICE TO HAVE
- Quick Start Guide
- Lessons Learned
- Troubleshooting

---

## File Location

```
project/
├── CLAUDE.md          ← root level (main)
├── .claude/
│   └── commands/      ← custom slash commands
├── src/
│   └── CLAUDE.md      ← folder-specific context
```

---

## Multiple CLAUDE.md Files

**When to use:**
- Monorepo → 1 per package
- Different contexts → frontend/ vs backend/
- Team-specific → .claude/team-preferences.md

**Read order:** root first → then folder-specific

---

<!-- 3.3 Project Context -->

## Project Context: What to Include?

```markdown
## Project Context

### Project Overview
[What does this project do? 2-3 sentences]

### Architecture
- Backend: [Framework, Language, DB]
- Frontend: [Framework, Libraries]
- Infrastructure: [Hosting, CI/CD]
```

---

## Example: Tech Stack

```markdown
## Project Context

### Architecture
- **Backend**: Go + Fiber + PocketBase
- **Frontend**: Next.js 14 + Tailwind
- **Infrastructure**: Docker + Fly.io
- **Key Libraries**:
  - zod (validation)
  - tanstack-query (data fetching)
```

---

## Example: Goals & Constraints

```markdown
### Current Goals
- Launch MVP by January 2025
- Support 1000 concurrent users
- Mobile-first design

### Constraints
- Budget: Free tier only
- Team: Solo developer
- Timeline: 2 weeks
```

---

<!-- 3.4 Safety Rules -->

## Why Safety Rules?

AI มี power มาก = **ทำพังได้ง่าย**

### ❌ เคยเกิด:
- git push --force → history หาย
- rm -rf → ลบผิด folder
- gh pr merge → merge โดยไม่ review

### ✅ Solution: กำหนด rules ชัดเจน

---

## Never Force

```markdown
## 🔴 Critical Safety Rules

### Command Usage
- **NEVER use `-f` or `--force` flags**

### Git Operations
- Never git push --force
- Never git checkout -f
- Never git clean -f

### File Operations
- Never rm -rf → use rm -i
```

---

## Never Merge Without Permission

```markdown
⚠️ NEVER MERGE PRs WITHOUT EXPLICIT USER PERMISSION

- Never use gh pr merge unless instructed
- Always wait for user review
- Provide PR link, let user decide
```

```bash
# ❌ Wrong
gh pr merge 123

# ✅ Right
echo "PR ready for review: #123"
```

---

## Safe Command Patterns

```bash
# ❌ Dangerous
rm -rf node_modules
git push -f origin main
pnpm install --force

# ✅ Safe
rm -ri node_modules  # interactive
git push origin main  # no force
pnpm install         # normal
```

---

<!-- 3.5 Development Workflows -->

## Testing Discipline

```markdown
## Manual Testing Checklist

Before pushing any changes:
- [ ] Run build successfully
- [ ] No new warnings or type errors
- [ ] Test affected features
- [ ] Check console for errors
- [ ] Test mobile responsive
```

---

## GitHub Workflow

```
Issue → Branch → Code → Test → PR → Review → Merge
```

```bash
1. gh issue create --title "feat: ..."
2. git checkout -b feat/issue-123
3. # code...
4. # test...
5. git push -u origin feat/issue-123
6. gh pr create
7. # wait for review
8. # user merges
```

---

## Git Commit Format

```
[type]: [brief description]

- What: [specific changes]
- Why: [motivation]
- Impact: [affected areas]

Closes #[issue-number]
```

**Types:** feat | fix | docs | style | refactor | test | chore

---

## Example Commit

```bash
git commit -m "feat: Add user authentication

- What: JWT-based auth with refresh tokens
- Why: Secure user sessions required
- Impact: All API routes now protected

Closes #45"
```

---

<!-- 3.6 Short Codes -->

## What are Short Codes?

Short codes = **keyboard shortcuts สำหรับ AI**

แทนที่จะพิมพ์:
> "สร้าง GitHub issue เก็บ context แล้ว compact"

พิมพ์แค่: **ccc**

AI รู้ว่าต้องทำอะไร = **เร็วขึ้น 10x**

---

## Core 5 Short Codes

| Code | Purpose |
|------|---------|
| ccc | Context capture & compact |
| nnn | Create plan (auto-ccc) |
| gogogo | Execute the plan |
| lll | List project status |
| rrr | Session retrospective |

**Flow:** lll → nnn → gogogo → rrr

---

## How to Define Your Own

```markdown
## Context Management & Short Codes

### xxx - Your Custom Code
**Purpose**: [What it does]

**Steps**:
1. First action
2. Second action
3. Third action

**Example**:
gh issue create --title "..."
```

---

## Example: Custom Short Code

```markdown
### ddd - Deploy to Production
**Purpose**: Safe deployment workflow

1. Run all tests
2. Build production bundle
3. Create git tag
4. Push to main
5. Trigger deploy pipeline

pnpm test && pnpm build && git tag v1.x.x
```

---

<!-- 3.7 Lessons Learned -->

## Why Track Lessons?

AI ทำผิดซ้ำ = **เสียเวลา**

บันทึก Lessons Learned:
- **Pattern ที่ work** → ใช้ซ้ำได้
- **Mistake ที่เกิด** → ป้องกันได้
- **User preferences** → AI ปรับตัวได้

= **AI ฉลาดขึ้นทุก session**

---

## Pattern Format

```markdown
## Lessons Learned

### Patterns (ใช้ซ้ำได้)
- **Pattern**: Use parallel agents for analysis
- **Pattern**: 1-hour chunks are optimal

### Anti-Patterns (หลีกเลี่ยง)
- **Anti-Pattern**: Monolithic plans
- **Anti-Pattern**: Skip testing before commit

### Discoveries (ค้นพบใหม่)
- **Discovery**: ccc → nnn workflow สร้าง structure ดี
```

---

## User Preferences

```markdown
### User Preferences (Observed)

- **Prefers manageable scope** — tasks < 1 hour
- **Values phased approaches** — split big work
- **Time zone**: GMT+7 (Bangkok)
- **Language**: Thai casual + English technical
- **Style**: Direct, no fluff
```

AI จะสังเกตและบันทึก preferences เอง

---

# 🎉 สรุป

1. **CLAUDE.md** = DNA ของ project
2. **3 sections สำคัญ**: Context, Safety, Short Codes
3. **Version control** = track การเปลี่ยนแปลง
4. **Lessons Learned** = AI ฉลาดขึ้น

**Next:** ลองสร้าง CLAUDE.md ของคุณเอง!
