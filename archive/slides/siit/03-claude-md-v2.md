---
title: CLAUDE.md Overview
description: Part 3 of SIIT Workshop - Overview Version (15 slides)
---

# CLAUDE.md
## สอน AI ให้รู้จักคุณ

---

## ปัญหา

AI ไม่จำอะไรเลย = ต้องอธิบายซ้ำทุกครั้ง

---

## Solution

**CLAUDE.md** = Onboarding doc สำหรับ AI

AI อ่านไฟล์นี้ก่อนทุกครั้ง

---

## 3 สิ่งที่ต้องมี

| Section | ทำไม? |
|---------|-------|
| **Project Context** | AI รู้ว่า project คืออะไร |
| **Safety Rules** | ป้องกัน AI ทำพัง |
| **Short Codes** | Workflow ของคุณ |

---

## Project Context

```markdown
### Architecture
- Backend: Go + PocketBase
- Frontend: Next.js + Tailwind
- Deploy: Fly.io
```

บอก AI ว่า tech stack คืออะไร

---

## Safety Rules

```markdown
## 🔴 Critical Safety Rules

- Never use --force
- Never merge without permission
- Never rm -rf
```

บอก AI ว่า **ห้ามทำอะไร**

---

## Short Codes

| Code | ทำอะไร |
|------|--------|
| `lll` | ดู project status |
| `nnn` | สร้าง plan |
| `gogogo` | Execute plan |
| `rrr` | สรุป session |

**Flow:** lll → nnn → gogogo → rrr

---

## ccc → nnn → gogogo

```
ccc     = เก็บ context ไว้ก่อน
   ↓
nnn     = วางแผนงาน
   ↓
gogogo  = ลงมือทำ
```

---

## Lessons Learned

AI เรียนรู้จาก mistakes

```markdown
### Patterns
- 1-hour chunks are optimal

### Anti-Patterns  
- Monolithic plans = fail
```

---

## File Location

```
project/
├── CLAUDE.md       ← หลัก
└── src/
    └── CLAUDE.md   ← เฉพาะ folder
```

---

## ลองเลย!

1. สร้างไฟล์ `CLAUDE.md` ที่ root
2. ใส่ Project Context
3. ใส่ Safety Rules
4. ลอง `lll` → `nnn` → `gogogo`

---

# 🎉 สรุป

CLAUDE.md = **DNA ของ project**

3 สิ่งสำคัญ: Context, Safety, Short Codes
