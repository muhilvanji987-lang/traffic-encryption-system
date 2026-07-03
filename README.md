# 🔐 Encrypt.sys — Encryption, Decryption & Auto Traffic Enforcement System

A browser-based portfolio project combining **AES-128 encryption/decryption** (text, files, and images) with a fully interactive **Automated Traffic Enforcement demo** — plate scanning, speed calculation, automatic fine issuance, and licence auto-cancellation.

Built entirely with HTML, CSS, and JavaScript — no backend, no installation, runs directly in the browser.

---

## 🔗 Live Demo

Once deployed via GitHub Pages (see setup below), the live link will be:

```
https://muhilvanji987-lang.github.io/traffic-encryption-system/
```

---

## 📋 Table of Contents

1. [Features](#-features)
2. [How the Traffic Enforcement Flow Works](#-how-the-traffic-enforcement-flow-works)
3. [Tech Stack](#-tech-stack)
4. [Project Structure](#-project-structure)
5. [How to Run Locally](#-how-to-run-locally)
6. [How to Deploy on GitHub Pages](#-how-to-deploy-on-github-pages)
7. [How to Push Updates](#-how-to-push-updates)
8. [Limitations & Honest Notes](#-limitations--honest-notes)
9. [Authors](#-authors)

---

## ✨ Features

### 🔒 Encryption / Decryption Module
- **Text encryption/decryption** using AES-128 via the browser's native Web Crypto API
- **File encryption/decryption** — encrypt/decrypt any uploaded file
- **Image encryption/decryption** — encrypt/decrypt image bytes with before/after preview

### 🚦 Automated Traffic Enforcement Module
- **Plate scanning** — one-click "Scan [plate]" buttons for instant demo, or manual entry
- **RTO-style vehicle registry** — 8 pre-loaded vehicles with full owner profiles (name, phone, driving licence number, address, vehicle details), all AES-encrypted
- **Admin panel** — enroll new vehicles into the registry in advance (simulating a real RTO registration step, done *before* a vehicle is ever checked — not during a live stop)
- **Automatic speed calculation** from distance + time sensor inputs
- **Automatic fine issuance** — ₹500 base + ₹50 per km/h over the 60 km/h limit, doubled automatically on the 3rd+ offense
- **Real 3-day payment countdown** per fine
- **Automatic licence cancellation** if a fine goes unpaid past its 3-day window
- **"Simulate 3 Days Passing" demo button** — lets you preview the auto-cancellation instantly instead of waiting 3 real days

---

## 🔁 How the Traffic Enforcement Flow Works

```
🚗 Vehicle passes
   ↓
🔍 Officer scans the plate (one click in the demo)
   ↓
📋 Owner details load AUTOMATICALLY from the encrypted registry
   (no manual typing needed at the point of the stop — the vehicle
    was already registered in advance, like a real RTO record)
   ↓
⚡ Speed is calculated from distance/time sensor values
   ↓
💰 If over the limit, a fine is added to the owner's account automatically
   ↓
📅 A real 3-day countdown starts
   ↓
✅ Paid in time → case closed, licence stays valid
❌ Not paid in 3 days → licence is CANCELLED automatically
```

**Key design decision:** vehicle registration (entering full owner details) and live enforcement (scanning a plate) are deliberately separate steps — exactly like the real world. You don't fill out RTO paperwork while chasing a speeding car; the car was already registered long before that moment. The demo's Admin Panel simulates the advance-registration step; the Scan section simulates the real-time roadside check.

---

## 🛠 Tech Stack

- **HTML/CSS/JavaScript** — no frameworks, no build step, no dependencies
- **Web Crypto API** (`crypto.subtle`) — real AES-128 encryption, done client-side
- **100% client-side** — nothing is ever sent to a server; all data lives in browser memory during the session

---

## 📁 Project Structure

```
traffic-encryption-system/
├── index.html      ← the entire application (single file)
├── README.md         ← this file
└── .gitignore
```

---

## ▶️ How to Run Locally

No installation required.

1. Download `index.html`
2. Double-click it, or right-click → **Open with** → any browser (Chrome, Firefox, Edge)
3. That's it — the app runs immediately

---

## 🚀 How to Deploy on GitHub Pages

1. Push this repo to GitHub (see [Push Updates](#-how-to-push-updates) below if you need the commands)
2. In your repo: **Settings → Pages**
3. Under **Build and deployment**, set:
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
4. Click **Save**
5. Wait about a minute, then visit:
   ```
   https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
   ```

---

## 🔄 How to Push Updates

**Using the GitHub website (no terminal needed):**
1. Open the file you want to update in your repo
2. Click the ✏️ pencil icon to edit, or delete + re-upload the new version
3. Scroll down, write a commit message, click **Commit changes**

**Using Git on the command line:**
```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
# replace index.html with your updated version
git add .
git commit -m "Describe what you changed"
git push
```

---

## ⚠️ Limitations & Honest Notes

- **Plate "OCR" is simulated**, not real optical character recognition. The one-click "Scan" buttons simulate a successful camera read; manual image upload falls back to filename matching for demo purposes. Real OCR (e.g. via Tesseract.js) could be added as a future improvement.
- **All data is in-memory only** — registering a vehicle or issuing a fine resets when the page is refreshed, since there's no real backend database. This is a client-side demo, not a production system.
- **Encryption is real** (genuine AES-128 via the Web Crypto API), but the "database" it protects is just a JavaScript object in the browser, not a real persistent store.
- This project is for **educational and portfolio purposes only** — it is not an actual government or law-enforcement system.

---

## 👤 Authors

Vanji Muthu P · S. Udhaiappan · D. Sathiyan
V.S.B. College of Engineering, 2026
