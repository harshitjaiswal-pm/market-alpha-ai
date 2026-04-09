# Business Strategy — MarketAlpha AI

**Version:** 0.1 (Concept)
**Author:** Harshit Jaiswal, Senior AI Product Manager
**Last Updated:** April 2026

---

## 1. Vision & Positioning

**One-line vision:** The AI co-pilot that helps individual investors systematically beat the market — without a quant team.

**Positioning:** MarketAlpha AI sits at the intersection of quantitative finance and LLM-powered reasoning. It is NOT a robo-advisor (no AUM, no fiduciary), NOT a data terminal (no Bloomberg pricing), and NOT a trading bot (no execution). It is a **research intelligence layer** — a signal engine that tells you what to look at and why.

---

## 2. Market Sizing

| Segment | Size | Source / Basis |
|---------|------|----------------|
| US retail investors with self-directed brokerage accounts | ~55M accounts | FINRA 2024 |
| Active traders (trade ≥ monthly) | ~15M | Estimated 27% of above |
| Willing to pay for research tools | ~3M | Estimated 20% of active traders |
| **Serviceable Addressable Market (SAM)** | **~3M users** | |
| Small RIAs (<$50M AUM) | ~9,000 firms | SEC RIA database |
| **Total Addressable Market (TAM) value** | **~$1.8B/yr** | At $50/user/month avg |

**Initial beachhead:** 1,000 active retail traders paying $29/month = **$29K MRR** within 12 months of launch.

---

## 3. Pricing Model

| Tier | Price | Features | Target |
|------|-------|----------|--------|
| **Free** | $0/month | 5 ticker analyses/day, 30-day backtest view | Acquisition & word-of-mouth |
| **Alpha** | $29/month | Unlimited analyses, full backtest history, watchlist digest | Core retail trader |
| **Pro** | $99/month | Portfolio overlay, sector heatmap, API access, priority signals | Power users & small RIAs |
| **Enterprise** | Custom | White-label, custom signal weighting, dedicated support | RIAs & family offices |

**Rationale:** $29/month is below the psychological friction threshold for a serious trader (~1.5× the cost of a Seeking Alpha subscription). At $99 for Pro, we're priced well below Bloomberg Lite ($300+/month) while offering AI-native workflow.

---

## 4. Competitive Landscape

| Competitor | Strength | Weakness | Our Differentiation |
|------------|----------|----------|---------------------|
| **Bloomberg Terminal** | Comprehensive data, institutional trust | $24K/year, steep learning curve | 100× cheaper, AI synthesis layer |
| **Seeking Alpha** | Strong community, analysis breadth | Human-authored, opinion-heavy, slow | Systematic, not editorial |
| **TrendSpider** | Strong charting & backtesting | Technical-only, no fundamental/sentiment | Multi-signal fusion (quant + LLM) |
| **Kavout / Signals** | AI signal generation | Black-box scores, limited reasoning | Transparent chain-of-thought |
| **ChatGPT / Claude** | General reasoning | No live data, no backtesting, not finance-native | Purpose-built for trading workflow |
| **Trade Ideas** | Real-time scanning | Rule-based only, no LLM synthesis | Natural language reasoning |

**Key insight:** No current product combines (a) real-time multi-source data aggregation, (b) LLM-powered reasoning synthesis, and (c) transparent backtesting in a single consumer-grade UI. That gap is the opportunity.

---

## 5. Go-To-Market Strategy

### Phase 1 — Validation (Months 1–3)
- **Channel:** Reddit (r/algotrading, r/investing, r/stocks) — post signal methodology transparently, let results speak
- **Goal:** 100 free users, 10 paying users, validate signal quality
- **Content:** Weekly "signal report" posts showing called shots vs. outcomes
- **Metric to unlock Phase 2:** ≥55% directional accuracy over 50+ signals

### Phase 2 — Growth (Months 4–9)
- **Channel:** LinkedIn (targeting RIA persona) + Twitter/X (finance influencer partnerships)
- **Channel:** Product Hunt launch once v1 UI is ready
- **Referral:** "Share a signal report" viral loop — users share analysis, embedded branding drives signups
- **Goal:** 500 free users, 100 paying Alpha subscribers
- **Metric to unlock Phase 3:** $5K MRR, NPS > 40

### Phase 3 — Scale (Months 10–18)
- **Channel:** SEO (long-tail: "AI stock analysis [ticker]", "is [company] a buy 2026")
- **Channel:** Direct RIA outreach via LinkedIn Sales Navigator
- **Partnership:** Integrate with Robinhood / IBKR via API for portfolio import
- **Goal:** $30K MRR, 50 Pro subscribers, 2 Enterprise pilots

---

## 6. Revenue Model & Unit Economics

**Assumptions (Month 12):**
- 800 free users (CAC: $0 via organic)
- 200 Alpha subscribers ($29/mo)
- 30 Pro subscribers ($99/mo)
- 0 Enterprise (pipeline building)

**Monthly Revenue:** (200 × $29) + (30 × $99) = $5,800 + $2,970 = **$8,770 MRR**

**Cost Structure (Month 12 estimate):**
- LLM API costs (OpenAI/Anthropic): ~$800/month (at ~$0.004/analysis, 200K analyses/month)
- Data APIs (Polygon, NewsAPI, FRED): ~$300/month
- Infrastructure (Vercel + Railway): ~$150/month
- **Total COGS: ~$1,250/month**

**Gross Margin:** ($8,770 − $1,250) / $8,770 = **~86%**

---

## 7. Key Risks & Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Signal edge disappears in live trading | Medium | High | Continuous backtesting, transparent methodology, set user expectations |
| SEC classifies output as investment advice | Low | Very High | Prominent disclaimers, "for informational purposes only" framing, consult legal before paid launch |
| LLM hallucination on financial data | Medium | High | Ground LLM on structured data only, output includes source citations |
| Large competitor copies feature set | Low | Medium | Speed to market, community trust, niche focus |
| Data API costs spike at scale | Low | Medium | Multi-provider fallback, cost modelling per user tier |

---

## 8. Founding Thesis

This product is built on a single falsifiable bet: **an LLM that synthesises quant signals, earnings context, news sentiment, and macro data can generate directional equity calls that outperform a passive S&P 500 strategy on a risk-adjusted basis.**

If the backtest proves this out, the business is defensible. If it doesn't, we pivot to the synthesis/research layer value prop (saving traders research time) independent of alpha generation.

Either way, the product explores a real and growing gap in the market.
