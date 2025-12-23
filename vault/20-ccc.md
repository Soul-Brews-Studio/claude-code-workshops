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

## Part of
[[30-ccc-nnn-gogogo-flow]]

## Related
- [[21-nnn]] — มักใช้หลัง ccc
- [[31-Two-Issue-Pattern]]
- [[11-Short-Codes]]

#short-code #ccc
