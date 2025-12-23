# ccc → nnn → gogogo Flow

Main workflow สำหรับทำงานกับ AI

## Flow
```
ccc → nnn → gogogo → rrr

เก็บ context → วางแผน → ทำ → สรุป
```

## Steps

### 1. [[20-ccc]] — Context Capture
เก็บ state ปัจจุบันไว้ก่อน

### 2. [[21-nnn]] — Create Plan
วางแผนงาน สร้าง plan issue

### 3. [[22-gogogo]] — Execute
ลงมือทำตาม plan

### 4. [[23-rrr]] — Retrospective
สรุป session, บันทึก lessons

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

## Related
- [[31-Two-Issue-Pattern]]
- [[11-Short-Codes]]

#workflow #main-flow
