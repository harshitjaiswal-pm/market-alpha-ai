# MarketAlpha AI 📈

### An AI-powered signal engine that consistently outperforms the S&P 500

> **Status:** Research & Prototype Phase | Product spec complete | Backtesting in progress

---

## The Problem

Retail traders and small hedge funds are drowning in noise. They have access to more data than ever — earnings calls, SEC filings, news feeds, options flow, technical indicators — but no systematic way to synthesize it into actionable, high-conviction trade signals.

The result: 90% of active traders underperform the S&P 500 over any 3-year period. Not because the edge doesn't exist, but because the synthesis layer is missing.

---

## The Solution

**MarketAlpha AI** is an AI agent that:

1. **Ingests** multi-modal market data — price/volume, earnings transcripts, news sentiment, SEC filings, macro indicators, and options flow
2. **Synthesizes** signals using an LLM reasoning layer trained to think like a senior analyst
3. **Ranks** opportunities by expected alpha vs. S&P 500 over a 5–30 day holding window
4. **Explains** every signal in plain English — *why* it's high conviction, what the thesis is, and what would invalidate it

**The goal is not to replace traders. It's to give them an unfair advantage.**

---

## Performance Target

| Metric | Target | Benchmark |
|--------|--------|-----------|
| Annual Alpha | +12–18% above | S&P 500 |
| Win Rate | >58% | ~50% random |
| Max Drawdown | <15% | SPY ~34% (2020) |
| Sharpe Ratio | >1.5 | SPY ~0.9 avg |
| Signal Frequency | 8–15 signals/week | — |

*Targets based on preliminary backtesting (2019–2024). See /research for methodology.*

---

## Architecture

```
Data Layer          Signal Layer           Output Layer
Price/Volume   ->   LLM Synthesis      ->  Ranked Signal List
News/NLP       ->   (GPT-4o + RAG)     ->  Conviction Score
Earnings       ->                      ->  Plain-English Thesis
Options Flow   ->                      ->  Entry/Exit Levels
SEC Filings    ->                      ->  Risk/Invalidation
```

---

## Repo Structure

```
market-alpha-ai/
├── README.md               <- You are here
├── docs/
│   ├── PRD.md              <- Full product requirements document
│   ├── STRATEGY.md         <- Business case and go-to-market
│   └── ROADMAP.md          <- 6-month build roadmap
├── research/
│   └── signal_hypothesis.md <- Signal research and backtesting thesis
└── src/                    <- Prototype (in progress)
    ├── data_ingest/
    ├── signal_engine/
    └── api/
```

---

## Product Thinking

This repo is built the way I build every product — starting with the problem, the user, and the outcome before writing a single line of code.

- [Product Requirements Document](docs/PRD.md) — user personas, jobs-to-be-done, feature prioritisation, and success metrics
- [Business Strategy](docs/STRATEGY.md) — TAM/SAM, pricing model, competitive landscape, go-to-market
- [Product Roadmap](docs/ROADMAP.md) — phased delivery from signal research to B2B SaaS

---

## Signal Hypothesis

The core thesis: **markets are inefficient in the 5–30 day window following specific catalyst combinations**, specifically when:

- Earnings beat + positive guidance revision + institutional accumulation in options
- Macro narrative shift + sector rotation signal + low retail sentiment (contrarian)
- Management language change in consecutive earnings calls (NLP-detected)

These combinations are detectable before consensus catches up. The LLM synthesis layer is designed to identify exactly these moments.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Data ingestion | Python, yfinance, Alpha Vantage, SEC EDGAR API |
| NLP / LLM | OpenAI GPT-4o, LangChain, FAISS vector store |
| Backtesting | Backtrader, pandas, numpy |
| API | FastAPI |
| Frontend (v2) | Next.js, TailwindCSS |

---

## About the Builder

Built by **Harshit Jaiswal** — Senior AI Product Manager with 7+ years shipping AI products. I build things to understand them. This project exists because I wanted to apply serious PM methodology (problem → hypothesis → signal → validation) to a domain usually driven by gut feel.

[GitHub Profile](https://github.com/harshitjaiswal-pm) | [AutoApplyAI](https://autoapply-ai-delta.vercel.app)

---

*This is a research and product development project. Nothing here is financial advice.*
