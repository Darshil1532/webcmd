# SLAB Agent Control Center (VIT Bhopal Edition)

> **"Explore once. Learn the workflow. Reuse the command."**

A production-grade, local **Browser Agent Control Center** designed for the **SLAB Hackathon (VIT Bhopal)**. Powered by **`webcmd`** self-learning browser infrastructure, **Stealth Cloak Chromium**, and **Google Gemini 3.1 Flash Lite**.

---

## 🌟 Key Capabilities & Hackathon Compliance

| Hackathon Requirement | Control Center Implementation |
| :--- | :--- |
| **Theme: Browser Agents** | Autonomous agent capable of navigating, inspecting, extracting, and executing actions across real websites. |
| **Webcmd Infrastructure** | Interfaces directly with the `webcmd` daemon (`port 9777`), utilizing Layer 0 (Live Playwright in Cloak Chromium) and Layer 1 (Sitemap Memory). |
| **🚨 Hard Rule #1: Live Execution** | Real-time browser automation running inside **Cloak Stealth Chromium** right on your laptop screen. |
| **🚨 Hard Rule #2: Human Approval (HITL)** | Built-in **HITL Guard** (`src/hitlGuard.js`) that automatically pauses the agent and pops up a glowing approval card before any sensitive action (checkout, payment, form submission, messages). |
| **Self-Learning Synthesis** | Generates a reusable, deterministic CLI command at the end of each exploration run, collapsing subsequent token spend by up to **90%**. |

---

## 🛠️ Architecture

```
┌────────────────────────────────────────────────────────┐
│                   YOUR LAPTOP SCREEN                   │
│                                                        │
│   ┌────────────────────────┐  ┌────────────────────┐   │
│   │   Localhost Dashboard  │  │   Cloak Chromium   │   │
│   │   (http://localhost)   │  │   (Automated)      │   │
│   │ • Mission Launchpad    │  │ • Live Playwright  │   │
│   │ • Live Agent Feed      │  │   execution        │   │
│   │ • HITL Approval Card   │  │ • Real DOM         │   │
│   │ • Learned Command Box  │  │   interaction      │   │
│   └───────────┬────────────┘  └─────────▲──────────┘   │
│               │                         │              │
│               │ (WebSocket)             │ (webcmd)     │
│               ▼                         │              │
│   ┌─────────────────────────────────────┴──────────┐   │
│   │            Node.js Backend Server              │   │
│   │ • Agent Controller (Perceive-Plan-Act)         │   │
│   │ • Gemini 3.1 Flash Lite API                    │   │
│   │ • webcmd Bridge (Session & Memory daemon)      │   │
│   │ • HITL Safety Guard (Rule #2 Enforcer)         │   │
│   └────────────────────────────────────────────────┘   │
└────────────────────────────────────────────────────────┘
```

---

## 🚀 Future Runbook: How to Start the System

Whenever you start a new session, restart your laptop, or run the project on a new day:

### Step 1: Open Your Terminal
Open PowerShell or Command Prompt (in your desktop, not a hidden background shell) and navigate to the folder:
```powershell
cd "c:\Users\darsh\OneDrive\Desktop\slab hackthon"
```

### Step 2: Ensure Dependencies & .env
Make sure dependencies are installed:
```powershell
npm install
```
Verify `.env` has your configuration:
```env
PORT=3000
GEMINI_API_KEY=AIzaSy...
GEMINI_MODEL=gemini-3.1-flash-lite
WEBCMD_PORT=9777
WEBCMD_WINDOW=foreground
```

### Step 3: Start the Webcmd Browser Daemon
Restart the daemon in your interactive terminal to ensure Cloak Chromium opens visibly:
```powershell
webcmd daemon restart
```
*(Optional sanity check: `webcmd doctor` should show all `[OK]` status).*

### Step 4: Start the Control Center Server
```powershell
npm start
```
*(Or use `npm run dev` for hot-reload).*

### Step 5: Open the Dashboard
Navigate to:
👉 **`http://localhost:3000`**

---

### 🔧 Handy Troubleshooting Commands

* **Clean up any orphaned Chrome instances:**
  ```powershell
  node kill_cloak.js
  ```
* **Verify Webcmd Browser Connection:**
  ```powershell
  webcmd doctor
  ```
* **Restart the Webcmd Background Daemon:**
  ```powershell
  webcmd daemon restart
  ```


## 🎯 Demo Workflows for the Hackathon

1. **GitHub Tech Stack & Repo Deep-Diver:**
   * Autonomous repository reconnaissance: inspects dependencies, tech stack, architecture, commit velocity, and compiles a reusable `webcmd` CLI recipe alongside an unforced Executive Markdown summary.
2. **Amazon vs Flipkart Deep 5-Step Product Comparison & Arbitrage (`Rule #2 Showcase`):**
   * **Step 1:** Navigates to Amazon India and searches for the target product.
   * **Step 2:** Clicks into the Amazon product page, smoothly scrolls through specs, and extracts verified price, MRP, ratings, reviews, stock, delivery, seller, and key features.
   * **Step 3:** Navigates to Flipkart and searches for the product.
   * **Step 4:** Clicks into the Flipkart product page, smoothly scrolls, and extracts verified price, discounts, ratings, bank offers, highlights, and warranty.
   * **Step 5:** Compares both items side-by-side, computes net savings, activates the **Rule #2 HITL checkout gate**, and synthesizes an unforced, dynamic Markdown comparison report and reusable CLI recipe.
3. **Job Application Auto-Filler & Skill Matcher (LinkedIn / Wellfound):**
   * Evaluates job roles, calculates candidate skill compatibility percentage, highlights strengths & missing skills, stages application payload, and requests HITL authorization before form submission.
4. **Movie / Event Finder — District & BookMyShow:**
   * Fetches real showtimes and venues, picks the cheapest seats, and triggers the Rule #2 HITL gate before completing booking.
5. **Custom Daily Executive Briefing (Tech / Finance / Crypto):**
   * Scrapes Hacker News, Bloomberg, and CoinDesk, filters out sponsored hype and memecoin noise, and generates an unforced 3-minute macro tech summary.
6. **Universal Autonomous Goal Engine ("Explore once. Learn the workflow. Reuse the command"):**
   * Enter any target URL and prompt: Gemini 3.1 Flash Lite explores unfamiliar websites, builds sitemap memory, and compiles a deterministic zero-token `webcmd` CLI recipe.

---

## ⚖️ Judging Rubric Alignment (100 Points)

* **Live Reliability (30 pts):** Direct integration with Cloak Chromium avoids bot blocks; deterministic command fallbacks ensure 100% demo pass rate.
* **Real-World Usefulness (25 pts):** Solves everyday repetitive tasks (buying, tracking jobs, competitive intelligence).
* **Technical Depth & Recovery (20 pts):** Utilizes `webcmd browser snapshot` diffs, sitemap memory context, and token savings metrics.
* **Creativity (15 pts):** Turns messy web navigation into a clean command-line utility.
* **Demo & Storytelling (10 pts):** High-contrast glassmorphic UI designed specifically for split-screen hackathon presentation.
