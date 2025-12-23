---
type: slides
topic: Tmux for Beginners
style: technical
---

# tmux สำหรับมือใหม่
## Terminal Multiplexer Tutorial

---

## 3 Concepts สำคัญ

### Session → Window → Pane

```
┌─────────────────┐
│     SESSION     │
│  ┌───────────┐  │
│  │  WINDOW   │  │
│  │ ┌───────┐ │  │
│  │ │ PANE  │ │  │
│  │ └───────┘ │  │
│  └───────────┘  │
└─────────────────┘
```

- **Session**: เก็บ state ของงานทั้งหมด (run background ได้)
- **Window**: เหมือน Tab ใน browser
- **Pane**: หน้าจอที่ถูกแบ่งใน 1 window

---

## ส่งคำสั่งไปยัง Session อื่น
### tmux send-keys

```bash
# ส่งคำสั่งไป run ที่ session อื่นโดยไม่ต้อง switch จอ
tmux send-keys -t my-session "ls -la" C-m
```

**Flow:**
1.  Session ต้นทาง (Automation Script)
2.  `send-keys -t target`
3.  Session ปลายทาง (Application) รับคำสั่งไปรัน

> เหมาะสำหรับทำ Automation หรือสั่ง restart server อัตโนมัติ

---

## Tmux Quick Reference
### ท่องจำเลย!

| Basics | Command |
|--------|---------|
| สร้าง session | `tmux new -s name` |
| ดู sessions | `tmux ls` |
| เข้า session | `tmux attach -t name` |
| ออก session | `Ctrl+b, d` |

| Splitting | Keys |
|-----------|------|
| แบ่งซ้าย-ขวา | `Ctrl+b, %` |
| แบ่งบน-ล่าง | `Ctrl+b, "` |
| สลับ pane | `Ctrl+b, arrows` |

| Windows | Keys |
|---------|------|
| สร้างใหม่ | `Ctrl+b, c` |
| ถัดไป/ก่อนหน้า | `Ctrl+b, n / p` |

<small>Prefix key: Ctrl+b</small>
