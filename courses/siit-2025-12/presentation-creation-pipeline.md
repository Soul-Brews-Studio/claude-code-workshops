# Presentation Creation Pipeline — Claude Code Courseware

**Purpose:** capture Digger's presentation-creation findings and convert them into a repeatable Thor workflow for future decks.

## Evidence patterns found

### 1. SIIT workshop convention

`claude-code-workshops` uses paired slide files:

```text
slides/siit/04-short-codes-v3.md
slides/siit/04-short-codes-v3.html
slides/siit/05-rrr-v3.md
slides/siit/05-rrr-v3.html
```

Pattern: `NN-topic.md` for source, `NN-topic.html` for rendered/public wrapper.

### 2. Phukhao course-folder convention

`phukhao-oracle/slides/blockchain-basics/` shows a richer teaching package:

```text
slides.md
syllabus.md
course-outline.md
evaluation-10-questions.md
image-prompts.md
quiz.html
quiz2.html
presentation.html
index.html
audio/p01.mp3 ...
images/p03_middleman.png ...
```

Use this pattern when a module becomes a full course, not just a slide deck.

### 3. Gemini slide prompt pattern

`Nat-s-Agents/ψ/outbox/gemini-slide-prompt-v6.md` shows a prompt format for presentation generation:

- title and theme
- audience
- duration
- language style
- design specifications
- exact slide count
- slide-by-slide content blocks
- visual metaphor per slide

Thor adaptation: use this to generate an optional visual/storytelling version of Hooks + Skills.

### 4. Corporate PPTX path

Digger flagged Anthropic `pptx` skill as alternate output path for corporate clients. Keep Reveal/HTML as workshop-native source; export or recreate in PPTX only when the client needs editable office files.

## Recommended Thor workflow

```text
1. Define course objective and audience.
2. Write lesson spine in Markdown.
3. Create 5-slide mini outline from pain → model → file → example → exercise.
4. Expand to full deck only after exercises are clear.
5. Pair slides with worksheets and facilitator notes.
6. Add quiz/evaluation if the module exceeds 90 minutes.
7. Run RRR after delivery and convert repeated issues into future skills/hooks.
```

## Hooks + Skills next refinements

- Split current 51-slide deck into variants:
  - 20-slide 60m beginner appendix
  - 35-slide 90m technical lab
  - 51-slide 3h ACC instructor lab
- Add screenshots or code screenshots for:
  - `SKILL.md` anatomy
  - `.claude/settings.json` hook config
  - blocked migration hook output
- Add Boy/Pinyo demo slide callouts.
- Add an evaluation quiz if using the 3-hour variant.

## Boy/Pinyo exact demo paths

Stable workshop copy for delivery: `courses/siit-2025-12/materials/hooks-skills/boy-dna-demo/`. Original Digger source is recorded in that directory's `README.md`.


### Simple skill: `skill_ccc.md`

`/opt/Code/github.com/Soul-Brews-Studio/claude-code-workshops/courses/siit-2025-12/materials/hooks-skills/boy-dna-demo/skill_ccc.md`

Teaching point:

- A real user independently packaged context capture as a skill.
- Trigger phrases are literal: `ccc`, `save context`, `context dump`.
- Body is procedural and concrete.

### Domain expert skill: `skill_peng-bookkeeping.md`

`/opt/Code/github.com/Soul-Brews-Studio/claude-code-workshops/courses/siit-2025-12/materials/hooks-skills/boy-dna-demo/skill_peng-bookkeeping.md`

Teaching point:

- Skill can encode voice, Thai domain triggers, file naming, tax audit, deadlines, and output formats.
- Shows why trigger descriptions need local language and real job vocabulary.
- Advanced contrast to `skill_ccc.md`: shortcut vs domain specialist.

### Provenance file

`/opt/Code/github.com/Soul-Brews-Studio/claude-code-workshops/courses/siit-2025-12/materials/hooks-skills/boy-dna-demo/PROVENANCE.md`

Teaching point:

- Keep received artifacts immutable.
- Use provenance to explain why demo material is evidence, not fabricated sample content.

## Slide-template rule

Every technical teaching deck should include:

1. Pain story.
2. Mental model table.
3. Smallest real file format.
4. Bad vs good example.
5. Live lab.
6. Exit ticket.
7. Follow-up skill/hook backlog.



## Rehearsal

Use `hooks-skills-rehearsal-checklist.md` before delivery to verify anchors, timing, demos, materials, and RRR capture.
