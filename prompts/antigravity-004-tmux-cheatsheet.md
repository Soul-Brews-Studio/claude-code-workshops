---
type: image
target: antigravity
status: pending
created: 2025-12-23
category: reference-card
---

# tmux Quick Reference Cheat Sheet

## Thai Text
Quick Reference
ท่องจำเลย!

## Prompt

```
Style: Cheat sheet, reference card, organized grid, clean typography
Composition: Two-column layout with organized command groups
Mood: Practical, reference material, print-friendly
Color palette: Deep blue (#1e40af) headers, black text, light gray backgrounds for sections

Subject: Printable tmux command reference card

Layout structure:

Header (top):
"tmux Quick Reference" (large, bold, centered)
"ท่องจำเลย!" (Thai subtitle)

Two-column grid layout:

LEFT COLUMN:
━━━━━━━━━━━━━━━━━━━━━━━
พื้นฐาน (Basics)
━━━━━━━━━━━━━━━━━━━━━━━
tmux new -s name     สร้าง session
tmux ls              ดู sessions
tmux attach -t name  เข้า session
Ctrl+b, d            ออก session

━━━━━━━━━━━━━━━━━━━━━━━
Panes
━━━━━━━━━━━━━━━━━━━━━━━
Ctrl+b, %            แบ่งซ้าย-ขวา
Ctrl+b, "            แบ่งบน-ล่าง
Ctrl+b, Arrow        สลับ pane

RIGHT COLUMN:
━━━━━━━━━━━━━━━━━━━━━━━
Windows
━━━━━━━━━━━━━━━━━━━━━━━
Ctrl+b, c            สร้างใหม่
Ctrl+b, n            ถัดไป
Ctrl+b, p            ก่อนหน้า
Ctrl+b, ,            ตั้งชื่อ

━━━━━━━━━━━━━━━━━━━━━━━
ขั้นสูง (Advanced)
━━━━━━━━━━━━━━━━━━━━━━━
send-keys -t name    ส่งคำสั่ง
capture-pane -p      จับภาพ

Design elements:
- Clean grid lines separating sections
- Monospace font for commands
- Thai and English labels
- Light gray background boxes for each section
- Easy to scan, well-organized
- Fits on one page when printed

Footer:
Small text: "Ctrl+b = Prefix key"

Technical:
--ar 16:9
--quality high
--style raw

Font: Use open source Thai fonts ONLY (Sarabun, Prompt, Kanit, Noto Sans Thai).
For commands: Use monospace font (Fira Code, JetBrains Mono, Source Code Pro).
DO NOT use commercial fonts.
```

## Visual Reference
- Similar to: Programming cheat sheets, keyboard shortcut cards
- Avoid: Too dense, small fonts, cluttered

## Expected Output
- Format: PNG
- Resolution: 1920x1080 (16:9)
- Usage: Quick reference slide, printable handout
- Save: claude-code-workshops/slides/visuals/004-tmux-cheatsheet.png
