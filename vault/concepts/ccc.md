# ccc

**Context Capture & Compact**

## What it does
1. รวบรวม state ปัจจุบัน
2. สร้าง GitHub issue (context issue)
3. Compact conversation

## When to use
- ก่อนจะเปลี่ยน task
- ก่อน context หาย
- ก่อนใช้ [[nnn]]

## Commands
```bash
git status --porcelain
git log --oneline -5
gh issue create --title "context: ..."
```

## Part of
[[ccc-nnn-gogogo-flow]]

## Related
- [[nnn]] — มักใช้หลัง ccc
- [[Two-Issue Pattern]]

#short-codes #ccc
