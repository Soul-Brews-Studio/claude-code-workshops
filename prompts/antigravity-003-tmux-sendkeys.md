---
type: image
target: antigravity
status: pending
created: 2025-12-23
category: tutorial-diagram
---

# tmux Send-Keys Flow Diagram

## Thai Text
ส่งคำสั่งไปยัง Session อื่น
tmux send-keys

## Prompt

```
Style: Flow diagram, technical, clean, directional
Composition: Left-to-right flow showing command transmission
Mood: Technical but clear, process-oriented
Color palette: Deep blue (#1e40af), bright green (#059669), red accent (#dc2626)

Subject: Flow diagram showing tmux send-keys command transmission

Visual flow (left to right):

1. Left: Terminal window labeled "Session 1"
   - Contains: tmux send-keys command visible
   - Blue color theme

2. Center: Large arrow pointing right
   - Arrow labeled "send-keys -t session2"
   - Command text flowing along arrow

3. Right: Terminal window labeled "Session 2"
   - Contains: Command being received/executed
   - Green color theme (receiving)

Command flow visualization:
- Dotted line or animated-style arrow showing data flow
- Small code snippet box showing:
  tmux send-keys -t 2 "สวัสดี" C-m

Thai text overlay: "ส่งคำสั่งไปยัง Session อื่น" - top center, large
Thai text overlay: "tmux send-keys" - bottom, monospace font

Visual elements:
- Clean terminal windows (simplified, not full detail)
- Clear directional flow
- Color coding: blue (sender) → green (receiver)
- White background
- Minimal, focused design

Technical:
--ar 16:9
--quality high
--style raw

Font: Use open source Thai fonts ONLY (Sarabun, Prompt, Kanit, Noto Sans Thai).
DO NOT use commercial fonts (PSL, DB, Helvetica Thai).
```

## Visual Reference
- Similar to: Network flow diagrams, process flowcharts
- Avoid: Overly complex, too many details, confusing arrows

## Expected Output
- Format: PNG
- Resolution: 1920x1080 (16:9)
- Usage: Advanced automation concept slide
- Save: claude-code-workshops/slides/visuals/003-tmux-sendkeys.png
