# Deploy to Cloudflare Workers
## Push to GitHub → Auto Deploy

---

## Why Cloudflare Workers?

| Feature | Benefit |
|---------|---------|
| Free tier | 100,000 requests/day |
| Fast | Global CDN (300+ locations) |
| HTTPS | Auto SSL certificate |
| Git Integration | Push = Deploy |

**URL ฟรี**: `your-name.workers.dev`

---

## How It Works

```
git push origin main
     ↓
GitHub receives push
     ↓
Cloudflare detects change
     ↓
Auto build & deploy
     ↓
Live at workers.dev
```

**ไม่ต้อง run command ใดๆ!**

---

## Project Structure

```
your-project/
├── wrangler.jsonc    ← config (3 lines!)
└── public/           ← static files
    ├── index.html
    ├── styles.css
    └── slides/
        └── *.html
```

**Rule**: ทุกอย่างใน `public/` = deploy ได้

---

## wrangler.jsonc

```jsonc
{
  "name": "your-project-name",
  "compatibility_date": "2025-01-01",
  "assets": {
    "directory": "./public"
  }
}
```

| Field | คืออะไร |
|-------|--------|
| `name` | ชื่อ subdomain (.workers.dev) |
| `compatibility_date` | Version ของ Workers API |
| `assets.directory` | Folder ที่จะ deploy |

---

## Step 1 - Connect GitHub

1. ไป **Cloudflare Dashboard**
2. Workers & Pages → Create
3. Connect to Git → Select repo
4. เลือก branch: `main`

**ครั้งเดียวจบ!**

---

## Step 2 - Configure Build

| Setting | Value |
|---------|-------|
| Build command | (leave empty) |
| Build output | `public` |
| Root directory | `/` |

**Static site = ไม่ต้อง build**

---

## Step 3 - Just Push!

```bash
# แก้ไขไฟล์
edit public/index.html

# Commit & Push
git add -A
git commit -m "update content"
git push origin main

# Done! Auto deploy ภายใน ~30 seconds
```

---

## Live Demo

```bash
# ดู current files
ls public/

# Push changes
git add -A && git commit -m "new slides" && git push

# เปิดดู (รอ ~30 sec)
open https://siit-claude-code-workshops.laris.workers.dev/
```

**Cloudflare จัดการทุกอย่าง**

---

## Check Deploy Status

**Cloudflare Dashboard:**
- Workers & Pages → your project
- Deployments tab
- ดู status: Success / Failed

**หรือดู GitHub:**
- Commit status check (green check)

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Deploy ไม่ update | Check branch ถูกไหม |
| 404 error | Check `assets.directory` path |
| Build failed | ดู Cloudflare logs |
| Wrong content | Clear cache / wait 30s |

---

## Key Takeaways

**3 สิ่งที่ต้องจำ:**

1. **Config** = `wrangler.jsonc` (3 lines)
2. **Connect** = GitHub repo → Cloudflare (ครั้งเดียว)
3. **Deploy** = `git push` (ทุกครั้งที่ update)

```
git push = deploy
ง่ายแค่นี้!
```
