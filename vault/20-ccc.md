# ccc

**Context Capture & Compact**

## What it does
1. รวบรวม state ปัจจุบัน
2. สร้าง GitHub issue (context issue)
3. Compact conversation

## When to use
- ก่อนจะเปลี่ยน task
- ก่อน context หาย
- ก่อนใช้ [[21-nnn]]

## Commands
```bash
git status --porcelain
git log --oneline -5
gh issue create --title "context: ..."
```

## Flow Position
```
>>> [[20-ccc]] >>> [[21-nnn]] → [[22-gogogo]] → [[23-rrr]]
```
Part of: [[30-ccc-nnn-gogogo-flow]]

## Creates
Context issue → used by [[31-Two-Issue-Pattern]]

## Concepts
- [[10-CLAUDE-md]] — ccc defined here
- [[11-Short-Codes]] — one of Core 3

## Next
→ [[21-nnn]]

## Back to
- [[00-MOC]]

#short-code #ccc
