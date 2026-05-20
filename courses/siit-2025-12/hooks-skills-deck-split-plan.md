# Hooks + Skills Deck Split Plan

Current master deck: `slides/siit/08-hooks-skills.md` — 54 slides after adding presentation creation and Boy callouts.

Digger flagged that existing workshop decks are usually ~11-15 slides. Treat the 54-slide deck as a **master deck**, not always a single delivery deck.

## Recommended variants

| Variant | Target | Slides | Use when |
|---|---:|---:|---|
| `08a-skills` | 60-minute beginner appendix | ~20 | SIIT full-day has limited time |
| `08b-hooks` | 90-minute technical lab | ~35 | learners can edit `.claude/settings.json` safely |
| `08c-acc-instructor` | 3-hour ACC 2026 lab | full 54 | instructor team / advanced cohort |

## 08a — Skills-first 60m

Keep:

1. Learning Goal
2. Mental Model
3. Compiler Ladder
4. Skill anatomy
5. Description gate
6. Bad vs Good
7. Exercise 1
8. Trigger matrix
9. Boy `skill_ccc.md`
10. Boy `skill_peng-bookkeeping.md`
11. Homework

Cut or mention quickly:

- hook implementation details
- Stop hook
- presentation pipeline
- subagent chaining

Outcome: one skill draft and trigger matrix.

## 08b — Hooks lab 90m

Keep:

- Mental model
- Hooks anatomy
- events/matchers
- migration-protection hook
- payload observation worksheet
- safety ladder
- skill+hook pairing
- tests as truth

Outcome: one hook design card and one warn-only hook.

## 08c — ACC instructor 3h

Use full master deck plus:

- ACC proposal
- worksheets
- presentation-creation pipeline
- facilitator notes
- optional quiz/evaluation

Outcome: instructors can teach the module and adapt it.

## Skip-to-section anchors for live delivery

If using the master deck live, instructor should announce:

```text
Beginner? Stop after Skills + Trigger Matrix.
Technical lab? Continue through Hooks.
Instructor track? Continue through Presentation Creation and RRR.
```

## File-generation rule

Do not physically split files until after one rehearsal. First use the master deck and note actual timing. Then split only if timing evidence proves it.



## Rehearsal

Use `hooks-skills-rehearsal-checklist.md` before delivery to verify anchors, timing, demos, materials, and RRR capture.
