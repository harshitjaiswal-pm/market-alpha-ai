# Product Requirements Document — MarketAlpha AI

**Version:** 0.1 (Concept)
**Author:** Harshit Jaiswal, Senior AI Product Manager
**Last Updated:** April 2026

---

## 1. Problem Statement

### Who is this for?
- **Primary:** Active retail traders (self-directed, $50K–$500K portfolio) who spend 5–15 hours/week on research but consistently underperform benchmarks
- **Secondary:** Small RIAs and family offices (<$50M AUM) that lack quant infrastructure but want systematic signal generation

### What is the core pain?
Traders have more data than ever but no systematic synthesis layer. They manually scan news, earnings, charts, and forums — a process that is slow, inconsistent, and emotionally biased.

### Why now?
LLMs have reached a capability threshold where multi-modal reasoning over financial data is feasible at low latency. No product currently combines structured quant signals with unstructured LLM synthesis in a consumer-grade interface.

---

## 2. Goals & Success Metrics

| Goal | Metric | Target (6 months post-launch) |
|------|--------|-------------------------------|
| Deliver alpha vs S&P 500 | Backtested Sharpe ratio | ≥ 1.2 |
| Reduce research time | Avg hours/week saved per user | 5+ hours |
| User retention | 30-day active retention | > 40% |
| Revenue | MRR | $10K+ |
| Signal accuracy | Win rate on directional calls | > 55% |

---

## 3. User Personas

### Persona A — "The Serious Hobbyist"
- **Profile:** 35–50 years old, $100K–$300K self-directed brokerage account, works full-time, trades evenings/weekends
- **Tools today:** Yahoo Finance, Seeking Alpha, Reddit, TD Ameritrade
- **Frustration:** Spends 2–3 hours reading before each trade, still second-guesses himself
- **Job to be done:** "Give me a confident, evidence-backed signal I can act on in under 10 minutes"

### Persona B — "The Small RIA"
- **Profile:** Independent advisor, $10M–$50M AUM, 1–3 person shop
- **Tools today:** Bloomberg Lite, Morningstar, gut instinct
- **Frustration:** Wants systematic signals but can't afford a quant team
- **Job to be done:** "Augment my research with a second opinion that doesn't have an agenda"

---

## 4. Feature Prioritisation (MoSCoW)

### Must Have (MVP)
- [ ] Multi-source signal aggregation (price action + news sentiment + earnings data)
- [ ] LLM synthesis layer: structured reasoning output per ticker
- [ ] Directional call output: BUY / HOLD / SELL with confidence score
- [ ] Backtesting harness: validate signals against 2y historical data
- [ ] Simple web dashboard: search ticker, view signal, view reasoning

### Should Have (v1.1)
- [ ] Watchlist with daily digest email
- [ ] Portfolio-level risk overlay
- [ ] Sector rotation heatmap
- [ ] Sharpe / drawdown tracking per signal type

### Could Have (v2)
- [ ] Brokerage API integration (paper trading)
- [ ] Custom signal weighting by user
- [ ] Mobile push notifications
- [ ] Social signal layer (Reddit/X sentiment)

### Won't Have (this phase)
- Automated trade execution
- Options pricing / derivatives signals
- Regulated investment advice

---

## 5. Technical Requirements

### Data Inputs
- **Price/Volume:** Yahoo Finance API or Polygon.io (free tier)
- **Earnings:** SEC EDGAR API (free)
- **News sentiment:** NewsAPI or GDELT
- **Macro indicators:** FRED API (free)

### Core Architecture
```
Data Ingest → Feature Engineering → Signal Model → LLM Synthesis → API → Frontend
```

### LLM Usage
- Primary: GPT-4o or Claude 3.5 for reasoning synthesis
- Prompt pattern: structured JSON context → chain-of-thought → structured JSON output
- Latency target: < 3s per ticker analysis

### Infrastructure (lean/prototype)
- Backend: Python (FastAPI)
- Data pipeline: Pandas + lightweight scheduler
- Frontend: React + Recharts
- Hosting: Vercel (frontend) + Railway (backend)

---

## 6. Out of Scope

- Real-time streaming data (batch/daily is sufficient for MVP)
- User authentication beyond basic login
- Multi-asset classes (crypto, forex, commodities) — equities only at MVP
- Compliance / regulatory filings

---

## 7. Open Questions

1. **Data cost at scale:** Can we stay within free API tiers up to 500 daily active users?
2. **LLM cost per query:** At 1000 analyses/day, what's the monthly OpenAI bill? Need cost model.
3. **Signal edge validity:** Does the backtested edge survive transaction costs and slippage?
4. **Legal:** Do signal outputs constitute "investment advice" under SEC definitions? Need legal review before paid launch.
5. **Distribution:** Is the core channel Reddit communities (r/investing, r/algotrading) or LinkedIn (for RIA persona)?

---

*This is a concept-stage PRD. The goal is to validate the core hypothesis — that an LLM-augmented signal layer can systematically outperform a buy-and-hold S&P 500 strategy — before committing to full product development.*
