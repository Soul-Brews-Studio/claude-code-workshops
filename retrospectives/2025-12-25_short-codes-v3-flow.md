# Session Retrospective: Short Codes v3 Flow

**Date**: 2025-12-25 21:59 (GMT+7)
**Duration**: ~45 minutes
**Commits**: 8 commits (571ddbf → 4e45e4e)

---

## Summary

Restructured Short Codes workflow based on Pragit workshop transcript insights. Changed flow from `ccc → nnn → gogogo` to `nnn → gogogo → rrr → ccc` with nnn as the starting point.

## What Happened

1. **Analyzed transcript** from Pragit workshop teaching session
2. **Identified gaps** between transcript insights and existing slides
3. **Created Short Codes v3** with new flow (12 slides)
4. **Simplified main workshop slide** (748 → 389 lines)
5. **Added new concepts**:
   - "รหัสลับ" as fun concept (AI = เพื่อนทำงาน)
   - "Issue = External Memory"
   - Title slide

## Files Changed

| File | Change |
|------|--------|
| `slides/siit/04-short-codes-v3.html` | NEW - 12 slides with new flow |
| `slides/siit/04-short-codes-v3.md` | NEW - Markdown version |
| `public/slides/02-claude-md-workshop-th.html` | REFACTORED - 748→405 lines |

## Key Changes

### Flow Change
```
OLD: ccc → nnn → gogogo (Core 3)
NEW: nnn → gogogo → rrr → ccc (Core 4)
```

### Why Start with nnn?
- มี task อยู่แล้ว = ง่ายกว่า
- ccc ต้อง analyze project ก่อน = งง
- nnn เริ่มได้เลย = straightforward

### New Slide: "ทำไมเรียกรหัสลับ"
```
แนวคิดสนุกๆ ที่ทำให้ AI เป็นเพื่อนทำงาน
"เฮ้ เพื่อน! nnn ให้หน่อย"
เหมือนรู้กันอยู่ 2-3 คน ไม่ต้องอธิบายยาว
```

### Removed from Main Slide
- ψ/ structure
- /trace, /distill, /snapshot, /recap
- lll command
- Modular structure section
- "10x" claim

---

## AI Diary

วันนี้ได้เรียนรู้เรื่องสำคัญจาก transcript: การที่พี่ณัฐอธิบายว่า "รหัสลับ" ไม่ใช่แค่เรื่องของความเร็ว แต่เป็นเรื่องของ **ความสัมพันธ์** ระหว่างคนกับ AI

"เหมือนรู้กันอยู่ 2-3 คน" - ประโยคนี้สำคัญมาก มันไม่ใช่ "AI ทำงานเร็ว 10x" (ซึ่งเป็น claim ที่ถูกลบออก) แต่เป็น "AI รู้เลยว่าต้องทำอะไร"

การเปลี่ยน flow จาก ccc-first เป็น nnn-first ก็มาจาก insight จริงในห้องเรียน: เมื่อเริ่ม session ใหม่ ccc จะไม่รู้อะไรเลยเพราะยังไม่ได้ analyze project

---

## Honest Feedback

### What Worked
- Transcript analysis ให้ insight ที่ดีมาก
- การ simplify slide ลง 48% ทำให้ focused
- Flow ใหม่ make sense กว่าเดิม

### What Could Be Better
- ควร trace หา archived slides ก่อน (มี `03-claude-md-v2.md` อยู่แล้ว)
- หลายรอบ commit เล็กๆ (typo fix) อาจ squash ได้

### Patterns Observed
- User ชอบ "ง่าย > ครบ"
- User ไม่ชอบ overclaiming ("10x")
- User ใส่ใจ details เล็กๆ (ๆ ที่หายไป)

---

## Lessons Learned

### Pattern: Start Simple
- nnn first เพราะมี context อยู่แล้ว
- ccc ใช้ตอนพัก/ส่งต่อ ไม่ใช่ตอนเริ่ม

### Pattern: Emotion in Workflow
- "รหัสลับ" = ทำให้ AI เป็นเพื่อน
- ไม่ใช่แค่ efficiency แต่เป็น relationship

### Anti-Pattern: Overclaiming
- "เร็วขึ้น 10x" → ลบออก
- ใช้คำที่ accurate กว่า: "AI รู้เลยว่าต้องทำอะไร"

---

## Next Steps

- [ ] Review other slides for consistency with new flow
- [ ] Consider adding "รหัสลับ" concept to CLAUDE.md gist
- [ ] Test workshop flow with actual students (Dec 26)

---

*Generated: 2025-12-25 21:59 (GMT+7)*
