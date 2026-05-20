# 08c — Presentation Creation
<!-- .slide: id="part-d-presentation" -->
## Turn Workflows into Teachable Courseware

---

## Learning Outcomes

By the end, instructors can:

1. Convert one workflow into a 5-slide mini lesson.
2. Choose Reveal/HTML vs PPTX output by audience.
3. Build a course folder with slides, worksheet, and evaluation.

---

## Pipeline

```text
lesson spine
  ↓
slide outline
  ↓
paired markdown/html deck
  ↓
lab handout + worksheet
  ↓
quiz / evaluation
  ↓
RRR after delivery
```

---

## SIIT Convention

`claude-code-workshops` pattern:

```text
slides/siit/NN-topic.md
slides/siit/NN-topic.html
public/slides/NN-topic.md
public/slides/NN-topic.html
```

Use paired source + public wrapper.

---

## Phukhao Course-Folder Pattern

For full courses, include:

```text
slides.md
syllabus.md
course-outline.md
evaluation-10-questions.md
quiz.html
image-prompts.md
audio/
images/
```

Use when module grows beyond one deck.

---

## Prompt Pipeline Pattern

Nat's `gemini-slide-prompt-v6.md` includes:

- theme
- audience
- duration
- language mix
- design specs
- slide count
- slide-by-slide content
- visual metaphor

This is a reusable presentation-generation skill pattern.

---

## Output Format Decision

| Path | Best for |
|---|---|
| Reveal/HTML | technical workshop, web delivery |
| Markdown source | version control and review |
| PPTX | corporate editable handoff |
| PDF | static archive |

Choose format last.

---

## Mini Deck Exercise

Turn your skill/hook into five slides:

| Slide | Content |
|---:|---|
| 1 | pain story |
| 2 | mental model |
| 3 | real file format |
| 4 | bad vs good |
| 5 | exercise / exit ticket |

---

## Evaluation Pattern

Phukhao style:

- 10 multiple-choice questions
- options ก/ข/ค/ง
- one obvious distractor
- one tempting wrong answer
- score card or answer key

Use evaluation to prove learning, not to punish.

---

## Distribution Strategy

| Audience size | Distribution |
|---|---|
| one person | zip / Vercel page |
| one team | repo folder + project skill |
| many teams | npm-style registry / plugin marketplace |

Boy's DNA package is a zip/Vercel proof case.

---

## RRR Close

After delivery, capture:

- where learners got stuck
- which prompts repeated
- which hook scared people
- which skill should be promoted
- what to cut from the deck

RRR feeds the next course version.

---

## Instructor Exit

Leave with:

1. one 5-slide outline
2. one worksheet
3. one evaluation question
4. one next skill/hook backlog item
