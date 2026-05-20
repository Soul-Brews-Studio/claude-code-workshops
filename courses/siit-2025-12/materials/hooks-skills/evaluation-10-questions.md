# แบบประเมินผล — Claude Code Hooks + Skills

Pattern adapted from Phukhao's `evaluation-10-questions.md`: 10 multiple-choice questions, ก/ข/ค/ง, with one obvious distractor and one tempting wrong answer.

## Questions

### 1. ถ้าอยากให้ Claude จำ convention ของโปรเจกต์ ควรเริ่มที่อะไร?

ก. Hook ทุกครั้ง  
ข. CLAUDE.md  
ค. ลบ context แล้วเริ่มใหม่  
ง. เปลี่ยน model

**Answer:** ข

### 2. ส่วนไหนของ `SKILL.md` สำคัญที่สุดต่อการ trigger?

ก. ชื่อหัวข้อ Markdown  
ข. จำนวน bullet ใน body  
ค. `description`  
ง. สีของ slide

**Answer:** ค

### 3. ข้อใดเป็น description ที่ดีกว่า?

ก. `Helps with deploy.`  
ข. `Make sure to use this skill whenever the user says "release", "ship", or "deploy prod". Do NOT trigger for local dev server.`  
ค. `Very useful workflow.`  
ง. `This is advanced.`

**Answer:** ข

### 4. ถ้าต้อง “ห้ามแก้ไฟล์ migrations เดิม” ควรใช้ layer ใด?

ก. CLAUDE.md อย่างเดียว  
ข. Hook แบบ `PreToolUse`  
ค. เปลี่ยนชื่อ repo  
ง. เพิ่ม emoji ใน prompt

**Answer:** ข

### 5. Hook event ใดเหมาะสำหรับ format หลังแก้ไฟล์สำเร็จ?

ก. `PostToolUse`  
ข. `PreCompact`  
ค. `Notification`  
ง. `SessionEnd`

**Answer:** ก

### 6. ทำไมควรเริ่ม hook เป็น warn/log ก่อน block?

ก. เพราะ hook block ไม่เคยทำงาน  
ข. เพื่อลด false positive และดู payload จริงก่อน  
ค. เพราะ Claude ไม่อ่าน stderr  
ง. เพราะ settings.json ห้าม commit

**Answer:** ข

### 7. Subagent เหมาะกับงานแบบใด?

ก. งานเฉพาะทางที่ใช้ context เยอะ เช่น security review  
ข. แก้ typo หนึ่งคำ  
ค. เปลี่ยนสีปุ่มทันที  
ง. เปิด browser แทน user เสมอ

**Answer:** ก

### 8. Skill กับ Hook ต่างกันอย่างไร?

ก. Skill บังคับทุกอย่าง, Hook เป็นเอกสารอ่านเล่น  
ข. Skill package workflow, Hook enforce invariant  
ค. Skill ใช้ได้เฉพาะ Python, Hook ใช้ได้เฉพาะ Markdown  
ง. ไม่มีความต่าง

**Answer:** ข

### 9. ใน presentation creation pipeline ควรเริ่มจากอะไร?

ก. เลือก animation ก่อน  
ข. lesson spine / learning outcome  
ค. export PPTX ทันที  
ง. ใส่ QR code ก่อนมีเนื้อหา

**Answer:** ข

### 10. Exit ticket ที่ดีที่สุดควรพิสูจน์อะไร?

ก. ผู้เรียนจำชื่อวิทยากรได้  
ข. ผู้เรียนมี skill/hook/action ต่อที่นำไปใช้จริง  
ค. ผู้เรียนเปิด slide ได้  
ง. ผู้เรียนไม่ถามคำถาม

**Answer:** ข

## Scoring

| Score | Interpretation |
|---:|---|
| 8-10 | Ready to implement a small skill/hook safely |
| 5-7 | Understands concepts; needs guided lab support |
| 0-4 | Re-teach layer model before implementation |

## Instructor notes

Tempting wrong answers are designed around common mistakes:

- overusing hooks for knowledge
- writing vague skill descriptions
- skipping payload observation
- choosing output format before lesson spine

