# CLAUDE.md

DNA ของ project — ไฟล์ที่ AI อ่านก่อนทุกครั้ง

## Why?
- AI ไม่จำ context → ต้องบอกทุกครั้ง
- CLAUDE.md = onboarding doc สำหรับ AI

## 3 Sections สำคัญ
1. **Project Context** — tech stack, goals
2. **Safety Rules** — ห้ามทำอะไร
3. **[[11-Short-Codes]]** — workflow ของคุณ

## Location
```
project/
├── CLAUDE.md          ← main
└── src/
    └── CLAUDE.md      ← folder-specific
```

## Short Codes ที่เกี่ยวข้อง
- [[20-ccc]] — เก็บ context ไว้ใน issue
- [[21-nnn]] — สร้าง plan issue
- [[22-gogogo]] — execute plan
- [[23-rrr]] — สรุป session, update CLAUDE.md

## Workflows
- [[30-ccc-nnn-gogogo-flow]] — main workflow
- [[31-Two-Issue-Pattern]] — context + plan

## Related
- [[11-Short-Codes]]
- [[12-Retrospective]] — lessons learned ถูก copy มาที่นี่

## Slides
- [[40-slide-claude-md]]

## Back to
- [[00-MOC]]

#concept #claude-md
