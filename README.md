# Deployment Guide

## Local (full experience — 3 engines + WebSocket + real Tor)

```bash
npm install
npx playwright install --with-deps chromium firefox webkit

# Real Tor (optional but recommended): the app auto-starts it on demand
sudo apt-get install tor        # macOS: brew install tor

npm run build && npm start
# open http://localhost:3000  (WS side-channel on :3001)
```

| Component | Behaviour |
|---|---|
| Engines | Chromium, Firefox, WebKit — real binaries, pooled |
| Streaming | WebSocket `PORT+1` (CDP screencast on Chromium) with HTTP fallback |
| Tor | **Real onion routing** through `127.0.0.1:9050` (auto-spawned). Missing binary ⇒ clearly-labeled simulated mode |
| Database | Local PostgreSQL via `DATABASE_URL` (history only — optional) |


## 📄 License

This project is licensed under the **Proprietary Source-Visible License (PSVL)**.

* **Allowed:** Personal, local execution for testing, learning, and private use.
* **Prohibited:** Public deployments (e.g., Vercel, Netlify, AWS), hosting as a SaaS service, commercial use, or AI training without explicit permission.

See the Lincese.md file for the full terms. For commercial inquiries or deployment requests, please contact the repository owner.
