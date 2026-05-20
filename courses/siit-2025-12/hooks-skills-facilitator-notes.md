# Facilitator Notes + Pricing/Timeline — Hooks + Skills

**Module:** Advanced Claude Code Hooks + Skills  
**Deck:** `slides/siit/08-hooks-skills.md`  
**Best audience:** learners who have already seen CLAUDE.md, short codes, and RRR  
**Tone:** advanced but practical; every concept must produce a file, table, or guardrail.

## 1. Recommended packages

| Package | Duration | Use when | Deliverables |
|---|---:|---|---|
| Add-on module | 60 min | Existing full-day beginner workshop | 1 skill draft + 1 hook design |
| Advanced lab | 90 min | Technical cohort / ACC instructor team | skill + trigger matrix + hook snippet |
| Instructor clinic | 3 hr | Team wants to teach this themselves | full mini-course, review loops, rubric, Q&A |
| Production adoption | half-day | Company wants project guardrails | committed project skill/hook policy + test gate |

## 2. Pricing logic (qualitative)

Adding Hooks + Skills changes workshop value because it moves from “using Claude Code” to “building reusable Claude Code infrastructure.”

Recommended pricing adjustment:

- **60-min add-on:** price as advanced module, not bonus appendix.
- **90-min lab:** price as hands-on implementation lab because every participant leaves with reusable artifacts.
- **3-hr instructor clinic:** price as train-the-trainer / curriculum IP transfer.
- **Corporate production adoption:** price higher because hooks affect team policy, security, and CI habits.

Do not sell hooks as magic automation. Sell them as risk reduction and repeatability.

## 3. 3-hour ACC 2026 Instructor Team version

| Time | Segment | Instructor move | Participant output |
|---:|---|---|---|
| 0:00-0:15 | Framing | show Thai guide workflow summary; define layers | pain inventory |
| 0:15-0:35 | Skill anatomy | live-create `release-checklist` | SKILL.md draft |
| 0:35-0:55 | Trigger accuracy | peer-review descriptions | trigger matrix |
| 0:55-1:10 | Break / setup | ensure `.claude/skills` paths work | working local files |
| 1:10-1:35 | Hooks anatomy | explain events/matchers and payload | hook design card |
| 1:35-2:00 | Hook lab | build migration-protection or formatter hook | hook script + settings snippet |
| 2:00-2:20 | Subagents + tests | when to split context; tests as truth | operating-system map |
| 2:20-2:45 | Presentation creation | use deck template; turn one pain into 5 slides | mini deck outline |
| 2:45-3:00 | RRR close | capture what becomes a future skill/hook | retrospective + next action |

## 4. Speaker notes by deck section

### Opening / mental model

Say: “ถ้าเราต้อง prompt ซ้ำ แปลว่าเรายังไม่ได้สร้างระบบ.”

Emphasize the compiler ladder:

1. prompt once
2. record if repeated
3. skill if reusable
4. hook if invariant
5. subagent if context-heavy

### Skills section

Do not spend too long on YAML. The important part is trigger accuracy.

Ask learners to say their trigger phrases out loud. Real phrases beat clever descriptions.

### Hooks section

Use the Thai guide contrast: CLAUDE.md is advisory, Hooks are deterministic. Then immediately add caution: deterministic does not mean “block everything.” Hooks are power tools.

### Composition section

Show pairings:

- release skill + Stop verification gate
- migration skill + PreToolUse migration block
- slide skill + markdown lint check
- RRR skill + retrospective existence check

### Closing

Close with: “The best prompt is the one you never type again.”

## 5. Presentation creation recipe for Thor/Digger

When creating future decks, use this pattern:

1. Start with a pain story.
2. Name the mental model in one table.
3. Show smallest possible file format.
4. Give a bad example and a good example.
5. Run a live exercise.
6. Provide a rubric.
7. End with homework that feeds future CLAUDE.md / skills / hooks.

For this module, the smallest file formats are:

- `SKILL.md`
- `.claude/settings.json`
- `.claude/hooks/*.py|sh`
- `.claude/agents/*.md`

## 6. Setup checklist

Before class:

- [ ] Claude Code installed and logged in.
- [ ] Demo repo has `.claude/skills/` and `.claude/hooks/` directories.
- [ ] Hook scripts are executable if shell needs it.
- [ ] No secrets in demo repo.
- [ ] Public slide wrapper can load `public/slides/08-hooks-skills.md`.
- [ ] Instructor has fallback screenshots if CDN or internet fails.

## 7. Known pitfalls to teach explicitly

- Hook blocks with vague messages confuse the agent.
- Hook commands should not run full test suites on every edit.
- Skill body quality does not matter if description never triggers.
- Slash commands, skills, and subagents are different surfaces; do not blur them for beginners.
- Project-level policies should be committed only after team agreement.

