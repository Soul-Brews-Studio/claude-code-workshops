# ccc → nnn → gogogo Flow

Main workflow สำหรับทำงานกับ AI

## Flow
```
ccc → nnn → gogogo → rrr

เก็บ context → วางแผน → ทำ → สรุป
```

## Steps

### 1. [[ccc]] — Context Capture
เก็บ state ปัจจุบันไว้ก่อน

### 2. [[nnn]] — Create Plan
วางแผนงาน สร้าง plan issue

### 3. [[gogogo]] — Execute
ลงมือทำตาม plan

### 4. [[rrr]] — Retrospective
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
- [[Two-Issue Pattern]]
- [[Short Codes]]

#workflow #main-flow
