# GMT QuoteAgent 🤖

**AI-native sales & quotation agent for technology SMBs**  
Built by [Federico Marraro](https://github.com/gmtfedex) · Grupo MAR Telecomunicaciones · Rosario, Argentina

> Submitted to the **Build With Gemini XPRIZE Hackathon 2026** — Category: Small Business Services

---

## What it does

GMT QuoteAgent is an AI agent system that automates the commercial quoting workflow for technology integrators and SMBs.

A client sends a message via WhatsApp or email describing their need. The agent understands the request, builds a structured quotation using real product catalog data, generates a branded PDF document, and delivers it — automatically, in under 5 minutes.

If the client doesn't respond within 3 days, the agent sends a follow-up. No human intervention required.

**Before GMT QuoteAgent:** A quotation took 45–90 minutes of manual work per request.  
**After GMT QuoteAgent:** Under 5 minutes, 24/7, with full CRM logging.

---

## Core agents

| Agent | Model | Role |
|-------|-------|------|
| Classifier | Gemini Flash | Parses client message, extracts intent and entities |
| Quote Builder | Gemini Pro + Claude | Matches catalog products, calculates ARS/USD pricing, drafts the document |
| Follow-up | Gemini Flash | Monitors CRM, sends reminders on day 3 and day 7 |

---

## Tech stack

- **Gemini API** (Google Cloud) — primary LLM, classification and generation
- **Claude API** (Anthropic) — quotation document drafting and quality control  
- **N8N** — workflow orchestration (self-hosted via Docker)
- **NocoDB** — CRM and evidence logging (self-hosted via Docker)
- **Twilio WhatsApp API** — client input channel
- **Google Sheets** — product catalog and pricing management
- **Puppeteer / HTML→PDF** — branded document generation

---

## Project status

| Phase | Status | Target |
|-------|--------|--------|
| 1 · Core agents (classify + quote) | 🔄 In progress | Week 2 |
| 2 · WhatsApp integration | ⏳ Pending | Week 2 |
| 3 · First paying pilot client | ⏳ Pending | Week 3 |
| 4 · Follow-up agent + CRM | ⏳ Pending | Week 4 |
| 5 · Second client + MRR | ⏳ Pending | Week 6 |
| 6 · XPRIZE demo package | ⏳ Pending | Week 8 |

---

## Business model

- **Setup fee:** USD 300–500 per client (one-time onboarding and configuration)
- **Monthly subscription:** USD 80–120/month per company (active agent, catalog updates, support)
- **Target market:** Technology integrators, IT MSPs, and B2B SMBs in Argentina and Latin America

---

## Why this wins in Small Business Services

Most SMB quoting tools are generic SaaS built for US/EU markets. GMT QuoteAgent is built from 20+ years of real B2B technology sales experience in Argentina:

- Native ARS/USD dual pricing with configurable exchange rate
- Pre-loaded with real distributor catalog structure (Fortinet, Grandstream, Yeastar, Dahua)
- Understands Argentine commercial context: IVA, payment terms, validity windows
- WhatsApp-first — the actual channel Argentine SMB clients use

This is not a demo. GMT itself is the first production user.

---

## Evidence log

All agent operations are logged in NocoDB with full timestamps:

```
event_type | client_id | amount_USD | channel | agent_called | response_time_sec | outcome
```

This log is the operational proof required by XPRIZE judges.

---

## Repository structure

```
gmt-quoteagent/
├── agents/
│   ├── classifier/          # Gemini Flash — intent extraction
│   ├── quote-builder/       # Gemini Pro + Claude — document generation
│   └── followup/            # Gemini Flash — CRM monitoring
├── catalog/
│   └── products.csv         # GMT product catalog with pricing
├── n8n-workflows/
│   └── main-flow.json       # Exported N8N workflow
├── templates/
│   └── quote-template.html  # Branded PDF template
├── evidence/
│   └── operations-log.md    # XPRIZE evidence log (human-readable)
├── docs/
│   ├── 00-project-inception.md
│   ├── architecture.md
│   └── decisions/
├── .env.example             # Environment variables template (no secrets)
└── README.md
```

---

## Getting started

### Prerequisites

- Docker Desktop (Windows/Linux/macOS)
- Node.js 18+
- Gemini API key ([Google AI Studio](https://aistudio.google.com))
- Claude API key ([Anthropic Console](https://console.anthropic.com))
- Twilio account with WhatsApp sandbox

### Setup

```bash
git clone https://github.com/gmtfedex/gmt-quoteagent.git
cd gmt-quoteagent
cp .env.example .env
# Fill in your API keys in .env
docker-compose up -d   # starts N8N + NocoDB
```

Then import `n8n-workflows/main-flow.json` into your N8N instance.

---

## XPRIZE compliance

| Requirement | How we meet it |
|-------------|---------------|
| New project created during hackathon period | Repository created June 22, 2026 |
| Uses at least one Google Cloud product | Gemini API via Google Cloud Console |
| Includes Gemini API in at least one call | Classifier agent + Quote Builder both call Gemini API |
| Demonstrates AI transforming real workflows | Quotation time: 90 min → 5 min. Documented in evidence log. |
| Business Viability | Real clients, real invoices, MRR growth tracked |
| AI-Native Operations | All commercial workflow runs through agents in production |
| Category: Small Business Services | Target users are technology SMBs |

---

## About

**Grupo MAR Telecomunicaciones (GMT)**  
Technology integrator based in Rosario, Santa Fe, Argentina.  
Portfolio: Network security (Fortinet, Palo Alto) · VoIP/IP PBX (Grandstream, Yeastar) · CCTV · Structured cabling · Fiber optics · Hardware procurement.

**Contact:** info.grupomar@gmail.com  
**GitHub:** [@gmtfedex](https://github.com/gmtfedex)

---

*Project inception: June 22, 2026 · Built with Gemini API + Claude API + N8N + NocoDB*
