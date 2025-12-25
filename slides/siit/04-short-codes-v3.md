---
title: Short Codes
description: Part 4 of SIIT Workshop - Overview (12 slides)
---

# Short Codes
## รหัสลับสำหรับ AI

---

## ปัญหา

พิมพ์ยาว = เสียเวลา

> "สร้าง GitHub issue เก็บ context วิเคราะห์โปรเจกต์ แล้ว compact conversation..."

---

## Solution

พิมพ์แค่: **nnn**

AI รู้ว่าต้องทำอะไร = เร็วขึ้น 10x

---

## Core 4 Short Codes

| Code | Purpose | When |
|------|---------|------|
| **nnn** | วางแผน | **START HERE** |
| **gogogo** | ลงมือทำ | มี plan แล้ว |
| **rrr** | สรุป session | จบงาน |
| **ccc** | เก็บ context | พัก/ส่งต่อ |

---

## nnn - Create Plan

**START HERE**

"วางแผนก่อนทำ"

1. วิเคราะห์ task/issue
2. Research codebase
3. สร้าง plan issue พร้อม steps

*ง่ายที่สุด - มี task อยู่แล้ว!*

---

## gogogo - Execute

**"ลงมือทำ!"**

1. หา plan issue ล่าสุด
2. Execute step-by-step
3. Commit & push

---

## rrr - Retrospective

**"สรุปบทเรียน"**

1. What happened?
2. What worked / failed?
3. Lessons learned
4. Update CLAUDE.md

---

## ccc - Context Capture

**"เก็บ context ไว้ก่อน"**

1. รวบรวม state ปัจจุบัน
2. สร้าง GitHub issue
3. Compact conversation

*ใช้ตอนพักงาน หรือส่งต่อให้คนอื่น*

---

## The Flow

```
nnn → gogogo → rrr → ccc

วางแผน → ทำ → สรุป → เก็บ context
```

---

## Issue = External Memory

**"ความจำสำรองภายนอก"**

| แบบ | ผลลัพธ์ |
|-----|---------|
| แชท | หายไปเมื่อปิด session |
| GitHub Issue | อยู่ถาวร + ดูง่าย |

*เปิด session ใหม่ → บอก AI อ่าน issue → ทำต่อได้เลย*

---

## สร้าง Short Code ของคุณเอง

```markdown
### ddd - Deploy
1. Run tests
2. Build production
3. Create git tag
4. Deploy to server
```

ใส่ใน CLAUDE.md → AI รู้ทันที

---

## สรุป

**Short Codes = เร็วขึ้น 10x**

```
nnn → gogogo → rrr → ccc
```

Start with **nnn** - ง่ายที่สุด!
