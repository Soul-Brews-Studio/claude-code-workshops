# ccc → nnn → gogogo Flow

Main workflow สำหรับทำงานกับ AI

## Flow
```
[[20-ccc]] → [[21-nnn]] → [[22-gogogo]] → [[23-rrr]]

เก็บ context → วางแผน → ทำ → สรุป
```

## Steps

### 1. [[20-ccc]] — Context Capture
เก็บ state ปัจจุบันไว้ก่อน
→ สร้าง context issue

### 2. [[21-nnn]] — Create Plan
วางแผนงาน สร้าง plan issue
→ สร้าง plan issue

### 3. [[22-gogogo]] — Execute
ลงมือทำตาม plan
→ Commit & push

### 4. [[23-rrr]] — Retrospective
สรุป session, บันทึก lessons
→ สร้าง [[12-Retrospective]] file

## Diagram
```
┌─────┐    ┌─────┐    ┌────────┐    ┌─────┐
│ ccc │ → │ nnn │ → │ gogogo │ → │ rrr │
└─────┘    └─────┘    └────────┘    └─────┘
  │          │           │            │
  ▼          ▼           ▼            ▼
Context    Plan       Execute      Retro
Issue      Issue      & Commit     File
```

## Pattern
[[31-Two-Issue-Pattern]] — Context + Plan issues

## Defined in
[[10-CLAUDE-md]]

## Concepts
- [[11-Short-Codes]]
- [[12-Retrospective]]

## Slides
- [[40-slide-claude-md]]
- [[41-slide-short-codes]]
- [[42-slide-rrr]]

## Back to
- [[00-MOC]]

#workflow #main-flow
