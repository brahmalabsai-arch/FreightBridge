# 🚛 FreightBridge — Transportation Tendering Platform with AI Chatbot Agent

> A full-featured transportation tendering web application with an embedded AI chatbot agent, built entirely using [Claude](https://claude.ai) by Anthropic.

![FreightBridge](https://img.shields.io/badge/FreightBridge-Transport%20Tendering-0B0E11?style=for-the-badge&labelColor=3B82F6)
![AI Agent](https://img.shields.io/badge/AI%20Agent-Botpress%20%2B%20Fallback-10B981?style=for-the-badge)
![Built With](https://img.shields.io/badge/Built%20With-Claude%20AI-F97316?style=for-the-badge)
![Cost](https://img.shields.io/badge/Cost-%240%20Free-success?style=for-the-badge)

---

## About This Project

FreightBridge is a practice project built to learn **real-world AI agent integration** into a working website. The entire project — website, chatbot logic, Botpress integration, and documentation — was developed through conversation with **Claude (Anthropic)** as an AI pair-programming partner.

### What It Demonstrates

- Building a realistic, multi-page web application from scratch
- Integrating an **AI-powered chatbot agent** (Botpress) into an existing website
- Understanding the **transportation tendering** domain and supply chain logistics
- Deploying a static site on **GitHub Pages** with zero backend and zero cost

---

## How It Works

```
┌─────────────────────────────────────────────────────────┐
│                    FreightBridge Website                 │
│                                                         │
│  ┌──────────┐  ┌──────────┐  ┌───────────────────────┐ │
│  │  CLIENT   │  │TRANSPORTER│  │    AI CHATBOT AGENT   │ │
│  │  Posts    │  │  Submits  │  │                       │ │
│  │  Tenders  │  │   Bids    │  │  Botpress (AI/LLM)   │ │
│  │           │  │           │  │     ── OR ──          │ │
│  │  Awards   │  │  Tracks   │  │  Built-in Fallback   │ │
│  │  Bids     │  │  Win Rate │  │  (pattern matching)  │ │
│  └──────────┘  └──────────┘  └───────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

**Clients (Shippers)** register and post freight tenders with detailed requirements — routes, cargo type, weight, vehicle specs, commercial terms, and compliance conditions. **Transporters (Carriers)** browse open tenders, submit competitive bids, and track their performance. An **AI Chatbot Agent** assists all users in navigating the platform and understanding logistics concepts.

---

## Features

### Website — Transportation Tendering Platform

**Client / Shipper Side**
- Company registration with GSTIN, industry sector, contact details
- Post tenders with 20+ configurable fields covering route, cargo, vehicle, timeline, and budget
- 10 real-world tender conditions (GPS tracking, insurance, late delivery penalties, POD requirements, MV Act compliance, E-Way Bill, etc.)
- Dashboard with tender management and bid evaluation
- Award bids to selected carriers

**Transporter / Carrier Side**
- Registration with fleet composition (LCV through Multi-Axle Trailers, Tankers, Reefers)
- Fleet details: size, operating regions, years in business, certifications (ISO, GPS/VLTD, FSSAI)
- Browse and filter tenders by cargo type and region
- Submit bids with rate, transit time, vehicle allocation, and compliance declarations
- Dashboard tracking all bids and win rate

**Demo Data — 6 Realistic Tenders**
- FMCG full-truckload (Mumbai → Delhi)
- Bulk coal transport (Dhanbad → Durgapur)
- Pharma cold chain / refrigerated (Nashik → Bangalore)
- Container movement (JNPT → ICD Tughlakabad)
- Last-mile LCV distribution (Chennai Metro)
- Petroleum tanker transport (Jamnagar → Kandla)

### AI Chatbot Agent — Dual System

The website includes a **dual chatbot system** that can switch between an AI-powered agent and an offline fallback:

| Feature | Botpress (AI Agent) | Built-in Fallback |
|---------|--------------------|--------------------|
| AI Model | GPT-powered via Botpress LLM | None (pattern matching) |
| Intelligence | Understands context, generates human-like answers | Matches keywords to pre-written responses |
| Cost | Free ($5/month AI credit from Botpress) | Zero |
| Handles unknown questions | Yes — reasons and responds | No — shows fallback message |
| Requires internet | Yes | No (works offline) |
| Setup | Botpress account + embed code | None (works out of the box) |

**Switching between them:** Change one line in `index.html`:
```javascript
const USE_BOTPRESS = true;   // AI-powered Botpress agent
const USE_BOTPRESS = false;  // Built-in fallback (default)
```

### Built-in Chatbot Capabilities (Fallback)

The pattern-matching fallback chatbot covers 25+ intents including:
- Platform navigation (register, post tender, submit bid, dashboard, award bids)
- Logistics terminology (FTL, LTL, dedicated fleet, spot shipment)
- Cargo types, vehicle types, payment terms
- Tender conditions and eligibility criteria
- Documents required, safety and compliance
- Quick-action suggestion buttons after each response

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5, CSS3, JavaScript (single file) |
| Styling | Custom CSS with CSS Variables, dark theme |
| Typography | DM Sans + Space Mono (Google Fonts) |
| Data Storage | Browser localStorage (no backend) |
| AI Chatbot | Botpress Cloud (free tier) + built-in JS fallback |
| Hosting | GitHub Pages |
| Development | Built entirely with Claude AI (Anthropic) |

**No frameworks. No build tools. No backend. No API keys needed. Zero cost.**

---

## Project Structure

```
freightbridge/
├── index.html            # Complete website + chatbot (everything in one file)
├── chatbot.html          # Standalone chatbot reference (for iframe/testing)
├── README.md             # This file
├── BOTPRESS_SETUP.md     # Step-by-step Botpress setup guide
└── freightbridge-ai-chatbot.jsx  # Claude API-powered chatbot (React artifact demo)
```

---

## Quick Start

### Run Locally
```bash
git clone https://github.com/YOUR_USERNAME/freightbridge.git
cd freightbridge
open index.html    # or just double-click the file
```

### Deploy to GitHub Pages
1. Create a new repository on GitHub (e.g. `freightbridge`)
2. Push the files:
   ```bash
   git init
   git add .
   git commit -m "FreightBridge - Transportation Tendering Platform"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/freightbridge.git
   git push -u origin main
   ```
3. Go to **Settings → Pages → Source: main branch, root /**
4. Your site will be live at `https://YOUR_USERNAME.github.io/freightbridge/`

---

## Activating the Botpress AI Chatbot

The Botpress AI agent is free (no credit card required). See `BOTPRESS_SETUP.md` for the full guide, but the short version is:

1. Sign up at [botpress.com](https://botpress.com) (free)
2. Create a bot → Add instructions about FreightBridge
3. Publish → Go to Webchat → Deploy Settings
4. Copy the embed code (two `<script>` lines)
5. Paste into `index.html` in the marked section
6. Change `USE_BOTPRESS = false` to `USE_BOTPRESS = true`
7. Push to GitHub — done!

**Botpress free tier includes:** 500 messages/month, $5 AI credit (given to you, not charged), 1 bot, webchat embedding. Your bot stops responding after the credit is used — you are never auto-charged.

---

## How to Use the Website

### As a Client (Shipper)
1. **Register** → Select "Client / Shipper" → Fill company details
2. **Dashboard** → Click "+ Post New Tender"
3. Fill in route, cargo, conditions → **Publish Tender**
4. View incoming bids → **Award** the best one

### As a Transporter (Carrier)
1. **Register** → Select "Transporter / Carrier" → Fill fleet details
2. **Browse Tenders** → Filter by cargo type or region
3. Click a tender → **Submit Your Bid** with rate and fleet info
4. Track your bids in the **Dashboard**

### Using the AI Chatbot
Click the chat bubble (bottom-right corner) and ask anything:
- "How do I post a tender?"
- "What is FTL vs LTL?"
- "Explain tender conditions"
- "How does eligibility work?"
- "What vehicle types are available?"
- "What documents do I need for bidding?"

---

## Development Story

This entire project was built through conversation with **Claude (Anthropic)** — from initial concept to final deployment. Here's how the development progressed:

1. **Research phase** — Claude searched the web for transportation tendering processes, freight procurement best practices, tender conditions, and logistics terminology to build a realistic platform
2. **Website development** — Built a complete single-page application with registration, tender posting, bid submission, dashboards, and demo data — all in one HTML file
3. **Built-in chatbot** — Created a pattern-matching chatbot with 25+ intents and a fuzzy matching engine
4. **Bug fixing** — Identified and fixed a critical flaw in the matching engine where short greeting patterns ("hi", "sup") were incorrectly matching as substrings of real words ("submit", "shipping"), causing nearly all queries to return the greeting response
5. **Botpress integration** — Researched free chatbot platforms, selected Botpress (free tier, no credit card), and wired up a dual-system where Botpress AI and the built-in chatbot can be toggled with one config change
6. **Claude API demo** — Built a separate React artifact using the Anthropic API to demonstrate a real AI-powered chatbot with context-aware, generative responses
7. **Documentation** — Created README, Botpress setup guide, and inline code documentation

**Key learnings captured:**
- Real-world AI agent deployment workflow
- Pattern matching vs. LLM-based chatbots (and why LLMs are necessary for production use)
- Embedding third-party AI services into existing websites
- Transportation domain knowledge (tendering, freight procurement, compliance)

---

## Possible Extensions

- Add real authentication (Firebase Auth / Supabase)
- Connect to a real database instead of localStorage
- Email notifications for new bids
- Analytics dashboard with charts (Recharts / Chart.js)
- Multi-language support
- Mobile-responsive improvements
- Rate comparison and analytics for transporters

---

## License

MIT License — Free to use for learning and practice.

---

<p align="center">
  <strong>Built with 🤖 Claude AI (Anthropic) — as a learning project for AI agent integration</strong>
</p>
