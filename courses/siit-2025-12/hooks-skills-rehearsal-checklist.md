# Hooks + Skills Rehearsal Checklist

**Purpose:** turn the current artifact set into a deliverable classroom run. Use after every rehearsal and before ACC/SIIT delivery.

## 1. Deck navigation check

Master deck: `slides/siit/08-hooks-skills.md`

Required anchors:

- `#/navigate`
- `#/part-a-skills`
- `#/part-b-hooks`
- `#/part-c-compose`
- `#/part-d-presentation`
- `#/boy-demo`
- `#/homework`

Variant decks:

- `08a-skills` starts at `#/part-a-skills`
- `08b-hooks` starts at `#/part-b-hooks`
- `08c-presentation-creation` starts at `#/part-d-presentation`

## 2. Timing rehearsal

| Variant | Target | Current slide count | Rehearsal rule |
|---|---:|---:|---|
| 08a Skills | 60m | 19 | max 2.5 min/slide including demo |
| 08b Hooks | 60-90m | 16 | reserve 25m for hook lab |
| 08c Presentation | 30m | 12 | reserve 10m for mini-deck exercise |
| Master / ACC | 180m | 55 | use breaks between 08a/08b/08c |

If a section overruns by >10 minutes, cut examples before cutting exercises.

## 3. Live demo readiness

### Skill demo

- [ ] Open `boy-demo-callouts.md`.
- [ ] Open Boy `skill_ccc.md`.
- [ ] Open Boy `skill_peng-bookkeeping.md`.
- [ ] Prepare one new demo `SKILL.md` in a throwaway repo.
- [ ] Run trigger matrix verbally before editing body.

### Hook demo

- [ ] Use throwaway repo only.
- [ ] Start with payload observation hook.
- [ ] Confirm `.claude/settings.json` path.
- [ ] Confirm hook script runs locally.
- [ ] Show warning/log before blocking.
- [ ] Block only a harmless fake migration edit.

### Presentation demo

- [ ] Open `presentation-creation-pipeline.md`.
- [ ] Open `gemini-slide-prompt-v6.md` as prompt-pattern evidence.
- [ ] Show Phukhao folder structure.
- [ ] Have learners fill 5-slide mini-deck table.

## 4. Boy demo dependency check

- [ ] Stable copy exists at `materials/hooks-skills/boy-dna-demo/`.
- [ ] `skill_ccc.md` opens from stable copy.
- [ ] `skill_peng-bookkeeping.md` opens from stable copy.
- [ ] `resonance_peng.md` opens from stable copy.
- [ ] `PROVENANCE.md` explains original source and frozen-evidence handling.

## 5. Materials check

- [ ] `materials/hooks-skills/worksheets.md`
- [ ] `materials/hooks-skills/evaluation-10-questions.md`
- [ ] `advanced-hooks-skills-module.md`
- [ ] `acc-2026-hooks-skills-proposal.md`
- [ ] `hooks-skills-facilitator-notes.md`
- [ ] `hooks-skills-deck-split-plan.md`
- [ ] `boy-demo-callouts.md`

## 6. Delivery decision tree

```text
If audience is mixed beginner → run 08a only, mention hooks conceptually.
If audience is technical and has laptops → run 08a + 08b.
If audience is instructor team → run 08a + 08b + 08c + evaluation.
If setup is unstable → skip live blocking hook; use payload observation and screenshots.
```

## 7. RRR after rehearsal

Capture:

- Which slide created confusion?
- Which demo took too long?
- Which trigger phrases learners naturally used?
- Which hook felt scary or unsafe?
- What should become a new skill?
- What should be cut from the master deck?

