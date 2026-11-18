# 📇 Card Details Extractor

A lightweight, privacy-first web app that captures details from **business cards and
invitation cards** — by pasted text **or** a card photo — and organises them into clean,
editable headings you can share instantly.

**Live demo (after you deploy):** `https://<your-username>.github.io/<your-repo-name>/`

---

## ✨ What it does

| Heading | Icon | What it captures |
|---|---|---|
| Name | 👤 | Person / addressee name (handles honorifics like Mr., Dr., Ms., Shri) |
| Address | 📍 | Street address, city, PIN/ZIP (understands Indian formats like "MG Road, Bengaluru 560001") |
| Email | ✉️ | Email address |
| Mobile | 📱 | Phone / mobile number — international formats (+91, +1, 00-), prefers "Mob:" over "Ph:" |
| Date | 📅 | "12th March 2026", "15/03/2026", "Sunday, 15th March 2026" — weighted toward invitation phrasing ("on…", "RSVP by…") |

### Input options
1. **Paste text** — copy text from a card (e.g. via your phone's Lens/camera text
   selection) and paste it in.
2. **Upload a photo** — click/drag & drop a card image; text is read **in your browser**
   with OCR (Tesseract.js), with a live progress bar.

### Output & sharing
- Every extracted field is **editable** — tap any field to correct it.
- Share options: **📤 Native share** (mobile), **📋 Copy all**, **🟢 WhatsApp**,
  **✉️ Email**, **👤 Save contact (.vcf)** (opens directly in phone contacts),
  **📄 Text file (.txt)**.
- Recent extractions are kept in a small **on-device history** you can reload anytime.

---

## 🚀 Deploy on GitHub Pages (free hosting)

1. **Create a repository** on GitHub — e.g. `card-extractor`.
2. **Add the files** — upload `index.html` and this `README.md` to the repository root
   (via *Add file → Upload files*, or `git push`).
3. **Enable Pages** — go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source: Deploy from a branch**,
   **Branch: `main`**, **Folder: `/ (root)`**, then click **Save**.
5. Wait 1–2 minutes, then open your site at:
   `https://<your-username>.github.io/<your-repo-name>/`
6. *(Optional)* Add a custom domain in the same Pages settings.

> No build step, no dependencies to install, no server, no environment variables —
> it's a single static HTML file.

---

## 💻 Run locally

- **Option A:** double-click `index.html` — it opens in any browser.
- **Option B:** serve it (`python3 -m http.server 8000` in the folder, then visit
  `http://localhost:8000`).

---

## 🔒 Privacy

- **Everything runs locally in your browser** — pasted text, uploaded images, and
  extracted details never leave your device. No analytics, no tracking, no server.
- History is stored only in your browser's `localStorage` (clear it with the
  *Clear history* button).
- The only network request is loading the OCR engine (Tesseract.js) from a public CDN —
  **on first use only**. After that it's cached and pasted-text mode works fully offline.
- No API keys are embedded anywhere in the code.

---

## 📁 Files

```
├── index.html   # the entire app (HTML + CSS + JS, self-contained)
└── README.md    # this file
```

---

## 📝 Notes & limits

- OCR accuracy depends on photo quality — sharp, well-lit, straight-on photos work best.
  Blurry or skewed shots may need small manual corrections (the editable fields make
  this easy).
- Extraction uses heuristic pattern matching tuned for common business/invitation card
  layouts (Indian & international formats). Unusual layouts may need quick manual fixes.
- Licensed under MIT — use, modify, and share freely.
