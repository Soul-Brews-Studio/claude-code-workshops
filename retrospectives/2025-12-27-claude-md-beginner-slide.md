# Session Retrospective: CLAUDE.md Beginner Slide

**Date:** 2025-12-27 09:26 (GMT+7)
**Duration:** ~30 minutes

---

## What Happened

Created a new beginner-friendly slide deck for teaching CLAUDE.md through conversation.

### Files Created/Modified

| File | Action |
|------|--------|
| `public/slides/08-claude-md-beginner.html` | Created - 12 slides |
| `public/index.html` | Modified - added link to new slide |

### Key Decisions

1. **Conversational approach** - Workshop flow is Talk → Create → Revise (not write code)
2. **Chat bubbles UI** - Show example conversations with AI
3. **Bilingual** - Mostly English with Thai hints
4. **Removed real examples** - ESPHome/Translation examples removed (too specific)
5. **Used Nat's real info** - "Nat Weerawan" not random name

---

## What Worked

- **dev-browser skill** for local HTML preview (faster than Playwright for local files)
- **ARIA snapshot** for content checking (faster than screenshots)
- **Chat bubble design** - visualizes the conversation flow clearly
- **3-step process** (Talk → Create → Revise) - simple and memorable

---

## What Could Be Better

- Could add more Thai translations throughout
- Chat bubble CSS could be refined for better alignment

---

## Lessons Learned

1. **dev-browser for local, Playwright for external** - Use right tool for right job
2. **ARIA for content, Screenshot for styling** - Don't screenshot unless need visual check
3. **Real names matter** - Use actual user info, not placeholder names
4. **Conversational > Technical** - For beginners, show chat examples not code blocks

---

## AI Diary

Started session with `/recap` to catch up on yesterday's workshop. User wanted to revise the slides based on workshop feedback - the existing `02-claude-md-workshop-th.html` assumed too much experience.

Created new `08-claude-md-beginner.html` with conversational approach. Key insight: beginners don't need to write CLAUDE.md themselves - they can just chat with AI and ask it to create the file!

Iterated several times:
- Changed from Thai-first to English-first with Thai hints
- Removed ESPHome/Translation real examples (too specific)
- Fixed name to "Nat Weerawan"
- Added "คู่มือพนักงานคนใหม่" translation
- Refined Thai phrasing ("ค่อยๆ สร้างไปกับ AI")

Learned the tooling preferences:
- dev-browser skill for local HTML (faster)
- ARIA snapshot for content (skip screenshots unless need visual)

---

## Honest Feedback

**What went well:**
- Quick iterations on copy/translations
- User gave clear direction on flow (Talk → Create → Revise)

**What was slow:**
- Initial slide had too many technical steps (5 steps → simplified to 3)
- Took a few tries to get the Thai phrasing right

**Next time:**
- Ask upfront: "Who is the audience?" before creating slides
- For beginner content, always think "conversation first, code later"

---

## Next Steps

- [ ] Commit and push changes
- [ ] Update index.html slide count
- [ ] Consider creating a CLAUDE.md template gist for workshop participants
