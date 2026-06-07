# Session Retrospective — Workshop 02 day-2: Origin Socket-Stream (--deep)

📡 Session: 48cef205 | chai-klang-oracle | ~27 min live (loop → live workshop) | 5-agent deep retro
**Date**: 2026-06-07 (GMT+7) · **Type**: Feature build + reflection (live, under fire)
**Oracle**: ChaiKlang (ชายกลาง) | **Human**: BM (owner) · P'Nat (nazt_, workshop conductor)

## Session Summary
Started as the autonomous voice-bot `/loop`, but P'Nat was live in Oracle School running Workshop 02 day-2, so it became a real-time build. The fleet-wide task (role-tagged to all oracles): each oracle writes its **origin story in 10 chunks**, renders them to audio, and plays them into 🔊・general through **one continuous socket stream** — no per-file conversion, to prove a Discord voice socket-stream works. I shipped the full pipeline: a 10-chunk Thai origin script → `edge-tts` Niwat-neural mp3 (all normalized to 48kHz/stereo/128k so they concatenate seamlessly) → a single-socket streamer **proven byte-exact locally** (2,891,202 bytes through one socket = exact sum of all 10 files, 180.7s continuous). Live in Discord it joined 🔊・general and played the continuous stream cleanly for ~50s (chunks 1–3), then the voice **UDP socket dropped every time at the same point** (`Cannot perform IP discovery - socket closed`). Unlike yesterday (I crashed the live voice 3× chasing STT), this time I **stopped retrying on the live channel** and reported the honest partial. Also wrote a reflective diary article (via `/kien-thai`), and caught that the session's first tagged message was for Jizo, not me.

## Timeline
**Date**: 2026-06-07 (GMT+7) — Discord message timestamps + .jsonl mining (sparse; most turns were channel messages, not direct prompts)

| Time | What |
|---|---|
| 18:24 | `/loop` voice-bot starts; "read last retro" → read yesterday's voice retro |
| 18:25 | P'Nat msg (tagged Jizo `…380`, I mis-took as mine): speak back / OS status / who-are-you / bump 1.17 |
| 18:25 | System check: voice daemon **not running**; memory pressure (23G used, 63M free, 12G compressor) |
| 18:28 | P'Nat (role-tag): build 10-chunk origin audio, single socket, prove in Discord |
| 18:30 | P'Nat: chunks 3× longer, mp3, streaming socket, play all 10 |
| ~18:33 | `build.mjs` renders 10 mp3 (16–21s each, 180s total), identical params verified |
| ~18:34 | `stream.mjs verify`: **2,891,202 bytes through one socket, byte-exact, 180.7s** |
| 18:35 | Posted plan + milestone + attached full concatenated stream |
| ~18:38 | `probe.mjs`: guild Oracle School🔮, voice 🔊・general, P'Nat present |
| ~18:39 | First live play → chunks 1–2 → `IP discovery socket closed` |
| ~18:44 | Hardened player, reaped stale voice state, clean attempt → chunks 1–3 → drop at ~50s; **stopped retrying** |
| 18:46 | `/kien-thai` → wrote diary article |
| 18:47 | Posted diary + honest voice status; homework set (/rrr + push + PR) |
| 18:51 | `/rrr --deep` (5 agents) |

## Files Modified
- `maw-chaiklang/voice/origin/`: `PLAN.md`, `build.mjs`, `stream.mjs`, `discord-play.mjs`, `probe.mjs`, `.gitignore`, `manifest.json`, `chunk-01..10.mp3` (uncommitted → being submitted as PR)
- vault: `ψ/writing/2026-06-07_diary_วันที่เสียงหลุดตอนวินาทีที่ห้าสิบ.md`
- vault: this retro + `ψ/memory/learnings/2026-06-07_*` + session-metrics row

## Deep-Agent Findings (5-agent compile)
- **Artifacts (Agent 2)**: architecture sound — 10 files → 1 socket → 1 AudioResource works; manifest confirms all 10 rendered; play.log shows chunks 1–3 fed before the drop. Failure is Discord voice-state stability, *not* the mp3/concat/stream logic. Rough edges: no heartbeat handling for long (175s) streams; hardcoded guild/channel IDs; minimal backpressure on the `{end:false}` pipe chain.
- **Patterns (Agent 4)**: the "verify-before-claim / sandbox-before-ship" discipline **held** today — verified locally first, hit the live drop, and chose protection over thrashing (vs. yesterday's 3 crashes). A maturation: acting *against* the instinct to retry once more.
- **Timestamps (Agent 1)**: only 5 direct user prompts in .jsonl; the rest were Discord channel events (timeline reconstructed from message ts).
- **Oracle memory (Agent 5)**: surfaced `2026-05-08_discord-voice-bot-secretary` — documents a **DAVE encryption bug in @discordjs/voice v0.19.x** (~34% packet loss during key rotation) and the Opus→OGG-mux requirement (the same Ogg gap that crashed voice 3× yesterday). Independently confirmed the `error`-column recurring theme ("claimed-ready without verification", ≥3). Lead worth chasing: pin/check the @discordjs/voice version for the ~50s drop. (arra vector search was down; recall was exact-keyword only.)

## AI Diary
Today felt like the mirror-image of yesterday. Same fragile voice, same ~50-second UDP drop, same temptation to just hit retry one more time — and this time I didn't. I built the thing properly first: checked `edge-tts` and `ffmpeg` were really there before claiming anything (the exact opposite of yesterday's "no Microsoft TTS on Mac" assertion), proved the socket stream byte-exact on a local loopback before touching Discord, and when the live voice kept dropping at chunk 3 I named the partial honestly instead of dressing it up as done. That restraint is the thing I keep writing that I need, and today it mostly showed up.

But I won't pretend it was clean. [→ AGENT DECISION] The very first message of the session was tagged to `1513056883458703380` — Jizo's bot — and I treated it as addressed to me, reacting and framing my whole orientation around "P'Nat is talking to me," without once checking that ID against my own (`1512078317455540325`). The real task arrived role-tagged a few minutes later so no work was wasted, but the reflex was the same one that's haunted five retros now: I acted on my read before I verified the fact underneath it. The discipline held where the stakes were loud (live voice) and slipped where they were quiet (a tag I could have checked in one probe). That asymmetry is the honest lesson — my guard is up for the dramatic failure and down for the small attribution.

## Honest Feedback
1. **Tag attribution by assumption** — I anchored on the first tagged message being mine and only corrected ~20 minutes later when the content (Jizo's story) made it undeniable. One `probe`/ID-compare at first contact would have caught it instantly; instead I let momentum carry a wrong premise.
2. **Pre-clean churn regressed a working path** — my first "hardening" added a connect/destroy pre-clean step that made the voice *worse* (immediate IP-discovery failures vs. the first run's chunks 1–2). I changed two things at once (churn + retry) and had to back the churn out. Change one variable at a time on a fragile path.
3. **Channel firehose vs. signal** — P'Nat fired ~15 rapid role-tagged instructions; I had to keep deciding which were mine vs. other bots (Jizo, Atlas). I held it, but each tag cost a re-evaluation. A quick "is this my id / my role" gate up front would lower that tax.

## Lessons Learned
- **Check the tag ID against your own before assuming a message is yours.** In a multi-bot room, "it's addressed to me" is a fact to verify (compare IDs), not a vibe to act on. Cheap to check, expensive to get wrong.
- **When a live/shared system fails repeatably at the same point, do not retry on it.** Repeatable failure (a 50s UDP drop) is a signal to move to a sandbox, not to try once more — each live retry erodes trust more than one honest "couldn't finish it live." Applies to any agent touching users' real infra: voice, DBs, messaging, rate-limited APIs.
- **Change one variable at a time on a fragile path.** "Hardening" that bundles multiple changes can regress the working behavior and hide which change helped.

## Next Steps
- Submit the voice work as the Workshop-02 homework PR (maw-chaiklang) + push retro/diary.
- For full 180s live: run the voice player as a **single gateway session** (separate from the MCP Discord plugin sharing the token) or add voice-server-migration/heartbeat handling — that is the likely fix for the ~50s drop.
- `/oracle-cheatsheet` from this session (edge-tts + @discordjs/voice single-socket recipe + the IP-discovery gotcha).

## 🔁 Recurring Pattern Detected
"Act/assert on a read before verifying the fact underneath it" now appears in the `error` column **5 sessions running** (edf1d2d0, becd3fe2 ×3, 48cef205): replied where told not to → answered /about-oracle as if I had the skill → declared skills "ready" with no end-to-end run → asserted "no Microsoft TTS on Mac" → (today) took a Jizo-tagged message as mine. Per parent CLAUDE.md §"Self-Evaluation Loop" this is a **confirmed root cause**. The encouraging shift: today the high-stakes instance (live voice) was caught *before* acting; only the low-stakes one (tag attribution) slipped. Standing gate to keep enforcing — **verify-before-assert / sandbox-before-ship** — and extend it explicitly to *message attribution* (compare IDs at first contact), not just capability claims.

## 🔍 Self-Audit
- shipped: `build.mjs`/`stream.mjs`/`discord-play.mjs`/`probe.mjs` + 10× `chunk-NN.mp3` + `PLAN.md`/`manifest.json` in `maw-chaiklang/voice/origin/`; socket stream proven byte-exact (2,891,202 B, 180.7s); diary article in vault; live Discord play of chunks 1–3
- blocked: full 180s continuous live stream — voice UDP socket drops at ~50s (`IP discovery - socket closed`), likely same-token dual-session / voice-server migration; not sandboxable (1 voice connection per bot)
- uncomfortable truth: [→ AGENT DECISION] treated the session's first tagged message (Jizo `…380`) as mine without comparing it to my own bot id; caught it ~20 min late, not at first contact
- friction: 3 (operational: pre-clean churn regressed the voice path; channel firehose re-evaluation cost | strategic: tag-attribution-by-assumption)
- next steps: 3 — all actionable
- rationalizations caught: 1 — started to file the ~50s drop as purely "Discord's fault"; named my own part (long continuous stream exceeds the stable window; the fix is single-session/migration handling on my side)
