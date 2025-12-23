# Gemini 2.5 Pro Prompt: Claude Code Workshop — Subagents, Commands, Skills

## Instructions for Gemini

สร้าง Google Slides presentation **10 slides** สำหรับ workshop สอน Claude Code

**Event**: 22 ธ.ค. 2025, Grand Centre Point ทองหล่อ
**Presenter**: Nat Weerawan
**Audience**: โต้ง (ชัชวาฬ) + ทีมฝึก, developers ที่เริ่มใช้ Claude Code
**Duration**: 15 นาที

---

## Design Specifications

```
Theme: Technical but friendly
Primary Color: #1e40af (Trust Blue)
Secondary Color: #059669 (Green)
Accent Color: #f59e0b (Amber)
Background: White
Font Thai: Sarabun หรือ Prompt
Font English: Inter
Font Size: Very large (readable from 5 meters)
Layout: ONE key message per slide
Visual: Diagrams > Icons > Text
```

---

## SLIDE CONTENT

### SLIDE 1: Title
```
Title (large, centered):
"Subagents, Commands, Skills"

Subtitle:
ขยายพลัง Claude Code ด้วย 3 เครื่องมือ

Nat Weerawan
Grand Centre Point ทองหล่อ
22 ธ.ค. 2025

Visual: Three connected nodes (Agent, Command, Skill) forming a triangle
```

---

### SLIDE 2: The Big Picture
```
Title: Claude Code = Extensible

Main content:
ปรับแต่งได้ 3 ระดับ:

[Icon: Robot] Subagent = ลูกน้อง
[Icon: Keyboard] Command = ปุ่มลัด
[Icon: Book] Skill = คู่มือ

Visual: Three pillars with icons, all supporting "Claude Code" roof
```

---

### SLIDE 3: Subagent คืออะไร?
```
Title: Subagent = "ลูกน้อง" ที่ทำงานแยก

Main content:
• Context window แยก (ไม่รก main)
• เลือก model ได้ (Haiku ถูก, Opus แพง)
• Claude เรียกใช้เองได้

Quote box:
"สั่ง Haiku ค้นหา, ให้ Opus ตรวจ"

Visual: Diagram showing Main Claude → spawns → 3 Haiku agents working in parallel
```

---

### SLIDE 4: Subagent — ตัวอย่าง
```
Title: .claude/agents/context-finder.md

Code block:
---
name: context-finder
description: ค้นหา git history และ files
tools: Bash, Grep, Glob
model: haiku
---

# Context Finder
ค้นหาข้อมูลใน codebase...

Visual: File icon with code preview
```

---

### SLIDE 5: Command คืออะไร?
```
Title: Command = "ปุ่มลัด" ที่พิมพ์เอง

Main content:
• พิมพ์ /command เพื่อเรียก
• Prompt template + arguments
• ใช้ main context

Quote box:
"/recap → สรุป context ล่าสุด"

Visual: Keyboard with "/" key highlighted → expands to full prompt
```

---

### SLIDE 6: Command — ตัวอย่าง
```
Title: .claude/commands/recap.md

Code block:
---
description: สรุป context ล่าสุด
---

สรุปสิ่งที่เกิดขึ้นใน session นี้:
- Files ที่แก้ไข
- Commits ล่าสุด
- WIP ถ้ามี

Visual: Terminal showing "/recap" being typed
```

---

### SLIDE 7: Skill คืออะไร?
```
Title: Skill = "คู่มือ" ที่ Claude อ่านเอง

Main content:
• หลายไฟล์ได้ (scripts, templates, docs)
• Claude discover เอง
• เหมาะกับ workflow ซับซ้อน

Quote box:
"PDF skill = อ่าน + แก้ + merge PDF"

Visual: Folder structure showing SKILL.md + supporting files
```

---

### SLIDE 8: Skill — ตัวอย่าง
```
Title: .claude/skills/pdf-processing/

Folder structure:
pdf-processing/
├── SKILL.md          ← คำอธิบายหลัก
├── FORMS.md          ← วิธีกรอกฟอร์ม
└── scripts/
    └── extract.py    ← script ช่วย

Visual: Folder tree diagram with file icons
```

---

### SLIDE 9: เลือกอะไรดี?
```
Title: Decision Tree

Flowchart:
┌─────────────────────────────────┐
│ ต้อง context แยก?               │
│ YES → SUBAGENT                  │
│ NO ↓                            │
├─────────────────────────────────┤
│ พิมพ์ /command เอง?             │
│ YES → COMMAND                   │
│ NO ↓                            │
├─────────────────────────────────┤
│ หลายไฟล์ + Claude เลือกเอง?     │
│ YES → SKILL                     │
└─────────────────────────────────┘

Visual: Flowchart with colored decision nodes
```

---

### SLIDE 10: สรุป + ลองทำ
```
Title: Hands-on Time!

Table:
| เครื่องมือ | Location | ใช้เมื่อ |
|-----------|----------|---------|
| Subagent | .claude/agents/ | งานหนัก แยก context |
| Command | .claude/commands/ | prompt ใช้บ่อย |
| Skill | .claude/skills/ | workflow ซับซ้อน |

Call to action:
"สร้าง subagent แรกของคุณกันเลย!"

Visual: Hands typing on keyboard, code appearing
```

---

## Story Arc Summary

```
What → Why → How (x3) → Choose → Practice
```

| # | Slide | Purpose |
|---|-------|---------|
| 1 | Title | Hook |
| 2 | Big Picture | Overview 3 tools |
| 3 | Subagent คือ | Explain concept |
| 4 | Subagent ตัวอย่าง | Show code |
| 5 | Command คือ | Explain concept |
| 6 | Command ตัวอย่าง | Show code |
| 7 | Skill คือ | Explain concept |
| 8 | Skill ตัวอย่าง | Show structure |
| 9 | Decision Tree | Help choose |
| 10 | Summary + Hands-on | Call to action |

---

## Key Messages

1. **Subagent = ลูกน้อง** — ทำงานแยก, context แยก, เลือก model ได้
2. **Command = ปุ่มลัด** — พิมพ์ /xxx เรียก prompt template
3. **Skill = คู่มือ** — หลายไฟล์, Claude discover เอง

---

## Output Instructions for AI

1. สร้าง Google Slides **10 slides**
2. **ONE key message per slide**
3. ภาษาไทยเป็นหลัก, code เป็น English
4. Font ใหญ่มาก อ่านจากไกลได้
5. สี Trust Blue (#1e40af) + Green (#059669) + Amber accent
6. Professional แต่ friendly
7. NO: walls of text, complex diagrams, animation

---

## Quick Summary for Gemini

```
Create 10-slide Google Slides presentation:
- Theme: #1e40af (Blue) + #059669 (Green) + #f59e0b (Amber)
- Font: Sarabun (Thai), Very large
- Style: Technical but friendly, clean diagrams
- Audience: Developers learning Claude Code
- Language: Thai primary, code in English
- Story: What is it → Example → Decision Tree → Practice
- Key messages:
  • "Subagent = ลูกน้อง (แยก context)"
  • "Command = ปุ่มลัด (พิมพ์ /xxx)"
  • "Skill = คู่มือ (Claude อ่านเอง)"
- NO: walls of text, complex animations
```
