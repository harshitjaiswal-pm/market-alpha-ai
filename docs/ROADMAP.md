# Product Roadmap — MarketAlpha AI

**Version:** 0.1 (Concept)
**Author:** Harshit Jaiswal, Senior AI Product Manager
**Last Updated:** April 2026
**Horizon:** 6 months (MVP to early traction)

---

## Roadmap Philosophy

This roadmap follows a **validate-then-build** approach. Before writing a single line of production code, the core signal hypothesis must be validated through backtesting. Each phase has a hard exit criterion — we don't move forward without evidence.

> "Build the smallest thing that proves the signal works. Then build the smallest thing people will pay for."

---

## Phase 0 — Signal Validation (Weeks 1–3)

**Goal:** Prove the alpha hypothesis before building any product.

**Exit criterion:** ≥ 55% directional win rate on 50+ backtested signals across at least 3 market sectors.

### Deliverables
- [ ] Set up data pipeline: Yahoo Finance API + FRED API + NewsAPI
- [ ] Build feature engineering notebook (price momentum, earnings surprise, sentiment delta)
- [ ] Implement baseline signal model (rule-based first, then ML layer)
- [ ] Run 2-year historical backtest (2022–2024)
- [ ] Calculate Sharpe ratio, max drawdown, win rate, avg gain vs. loss
- [ ] Document methodology and results transparently

### Stack
- Python (Pandas, yfinance, scikit-learn)
- Jupyter notebooks for exploration
- matplotlib / Plotly for visualisation

---

## Phase 1 — MVP: Signal Engine + Basic UI (Weeks 4–8)

**Goal:** Ship a working product that generates and displays signals for any US equity ticker.

**Exit criterion:** 10 external users (beta) actively using the tool and providing qualitative feedback.

### Deliverables

**Backend**
- [ ] FastAPI service: `POST /analyse/{ticker}` → returns signal + reasoning
- [ ] LLM synthesis layer: GPT-4o prompt chain (structured data in → JSON signal out)
- [ ] Daily data refresh scheduler (lightweight cron job)
- [ ] Basic signal logging to database (PostgreSQL on Railway)

**Frontend**
- [ ] React app: ticker search → signal card view
- [ ] Signal card: direction (BUY/HOLD/SELL), confidence score, 3-bullet reasoning summary
- [ ] Backtest chart: 6-month signal history vs. price chart
- [ ] Responsive design (desktop-first, mobile-readable)

**Infrastructure**
- [ ] Vercel deployment (frontend)
- [ ] Railway deployment (backend + DB)
- [ ] Environment config, secrets management

### Key Technical Risks
- LLM latency > 3s → mitigation: async generation + loading state
- Data API rate limits → mitigation: local caching layer

---

## Phase 2 — Monetisation & Retention (Weeks 9–16)

**Goal:** Convert beta users to paying subscribers. Reach $2K MRR.

**Exit criterion:** 50 paying Alpha subscribers ($29/month), 30-day retention > 40%.

### Deliverables

**Product**
- [ ] Auth system (Clerk or Auth0 — email + Google SSO)
- [ ] Free vs. paid tier gating (5 analyses/day free vs. unlimited paid)
- [ ] Watchlist feature: save tickers, receive daily digest email
- [ ] Email digest: daily summary of watchlist signals (SendGrid)
- [ ] Stripe integration: subscription billing (Alpha $29/mo, Pro $99/mo)

**Growth**
- [ ] Public signal log page (SEO-friendly: `/signals/AAPL`)
- [ ] "Share this signal" card — image export for Twitter/LinkedIn
- [ ] Reddit launch: post methodology + live signal calls in r/algotrading

**Analytics**
- [ ] PostHog integration: track search, analyse, subscribe events
- [ ] Weekly active user tracking
- [ ] Signal accuracy dashboard (internal)

---

## Phase 3 — Depth & Scale (Weeks 17–24)

**Goal:** Expand feature depth for power users. Reach $10K MRR.

**Exit criterion:** $10K MRR, NPS > 40, at least 1 RIA pilot agreement.

### Deliverables

**Product**
- [ ] Portfolio overlay: import holdings via CSV, get portfolio-level risk signal
- [ ] Sector rotation heatmap: which sectors are showing bullish/bearish consensus
- [ ] Macro context layer: integrate Fed rate signals, VIX regime detection
- [ ] Advanced backtester: user-configurable date ranges, signal type filters
- [ ] API access tier (Pro+): `/api/v1/signal/{ticker}` with API key

**Enterprise**
- [ ] RIA demo deck and pilot outreach (10 targeted firms)
- [ ] White-label pilot: custom branding, dedicated signal weights
- [ ] Compliance review: ensure "informational only" framing is legally sound

**Infrastructure**
- [ ] Move to AWS (ECS + RDS) if Railway hitting limits
- [ ] Cost optimisation: cache LLM outputs for 24h per ticker
- [ ] Rate limiting and abuse prevention

---

## Milestone Summary

| Milestone | Target Date | Success Metric |
|-----------|-------------|----------------|
| Signal hypothesis validated | Week 3 | ≥ 55% win rate, Sharpe ≥ 1.0 |
| MVP live (beta) | Week 8 | 10 beta users, daily active usage |
| First paying customer | Week 10 | 1 paid subscription |
| $2K MRR | Week 16 | 50 Alpha subscribers |
| Product Hunt launch | Week 14 | Top 5 of the day |
| $10K MRR | Week 24 | Mix of Alpha + Pro + 1 Enterprise pilot |

---

## What's Explicitly NOT on This Roadmap

- Automated trade execution (regulatory complexity, not the core value prop)
- Mobile app (web is sufficient for MVP)
- Crypto or forex signals (equities only to stay focused)
- Social trading / copy trading features
- Options / derivatives analysis

---

*This roadmap will be updated as we learn. The signal validation results in Phase 0 may change the direction of Phase 1 significantly.*
