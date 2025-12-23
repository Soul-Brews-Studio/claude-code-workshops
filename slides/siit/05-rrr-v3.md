---
title: rrr - Retrospective
description: Part 5 of SIIT Workshop (12 slides)
---

# rrr
## Session Retrospective

---

## ปัญหา

ทำเสร็จแล้ว... แล้วลืม

- ลืมว่าทำอะไรไป
- ลืม lessons learned
- ทำผิดซ้ำ

---

## Solution

**rrr** = สรุป session ก่อนจบ

บันทึกไว้ใน repo → AI จำได้ในครั้งหน้า

---

## rrr ทำอะไร? (5 Steps)

| # | Step |
|---|------|
| 1 | Gather data: git diff, git log |
| 2 | Create retrospective file |
| 3 | Validate checklist |
| 4 | Update CLAUDE.md |
| 5 | Commit & link to issue |

---

## Template Structure

```markdown
# Session Retrospective
- Date, Time, Duration
- Primary Focus, Session Type

## Session Summary
## Timeline
## Technical Details
## 📝 AI Diary ← MANDATORY!
## What Went Well
## What Could Improve
## 💭 Honest Feedback ← MANDATORY!
## Lessons Learned
## Next Steps
```

---

## 📝 AI Diary

⚠️ MANDATORY - ห้ามข้าม!

```markdown
## AI Diary

วันนี้เริ่มจาก issue #123
ตอนแรกคิดว่าง่าย แต่พอลงมือทำ
พบว่า API เปลี่ยนไป

ตัดสินใจ refactor แทน
User ชอบ approach นี้มาก
```

First-person narrative จาก AI

---

## 💭 Honest Feedback

⚠️ MANDATORY - ห้ามข้าม!

```markdown
## Honest Feedback

Session นี้ effective มาก
แต่ติดปัญหา context หายตอน compact

สิ่งที่ดี: ccc → nnn flow ช่วยมาก
สิ่งที่ต้องปรับ: ควร save context ก่อน
```

Frank assessment - พูดตรงๆ

---

## Lessons Learned

```markdown
### Pattern (ใช้ซ้ำได้)
- ccc → nnn → gogogo structure ดี

### Anti-Pattern (หลีกเลี่ยง)
- Plan ใหญ่เกินไป = fail

### Discovery (ค้นพบใหม่)
- User ชอบ overview มากกว่า detail
```

---

## Output

```
retrospectives/
└── 2025/12/
    └── 2025-12-23_14-30_retrospective.md
```

Commit แล้ว link ไป issue

---

## ✅ Validation Checklist

```markdown
Before Saving:
- [ ] AI Diary มี narrative จริง
- [ ] Honest Feedback มี assessment จริง
- [ ] Timeline มีเวลาจริง
- [ ] Lessons Learned actionable
- [ ] Next Steps specific
```

ถ้าไม่ครบ = retrospective ไม่มีค่า!

---

## The Full Flow

```
ccc → nnn → gogogo → rrr

เก็บ context → วางแผน → ทำ → สรุป
```

rrr = ปิด loop ให้สมบูรณ์

---

## 🎉 สรุป

**rrr** = ปิด session อย่างมีคุณค่า

- 📝 AI Diary — AI เล่าประสบการณ์
- 💭 Honest Feedback — พูดตรงๆ
- 📚 Lessons Learned — เรียนรู้จาก session

AI เรียนรู้ → ครั้งหน้าดีขึ้น
