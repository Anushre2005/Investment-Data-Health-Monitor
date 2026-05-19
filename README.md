![CI](https://github.com/Anushre2005/Investment-Data-Health-Monitor/actions/workflows/run_notebook.yml/badge.svg)
# 📡 Investment Data Health Monitor

A fully interactive, browser-based dashboard for monitoring the health of critical investment data — built with React, Recharts, and zero backend dependencies.

## 🚀 Live Demo
[View Live →](https://anushre2005.github.io/Investment-Data-Health-Monitor/)

## 📊 Features

| Tab | What it does |
|-----|-------------|
| **Dashboard** | RAG (Red/Amber/Green) KPI cards for 5 investment domains. Click any card to drill down into completeness, timeliness, validity, recon breaks, and SLA status. |
| **Anomaly Detection** | IQR-based outlier detection on 30-day share price series, with auto-generated plain-English summaries for each flagged anomaly. |
| **Exception Log** | Prioritised critical/warning exception log with an AI-generated summary of operational issues. |
| **Data Dictionary** | Filterable metadata catalog with field definitions, owners, refresh cadence, and data types for all domains. |

## 🏦 Investment Domains Covered
- Securities (reference data)
- Positions (portfolio holdings)
- Trades (execution records)
- Share Prices (market data)
- Client Data (CRM/KYC)

## 📐 KPI Definitions & RAG Thresholds

| KPI | Green | Amber | Red |
|-----|-------|-------|-----|
| Completeness | ≥ 95% | 80–95% | < 80% |
| Timeliness | ≥ 95% | 80–95% | < 80% |
| Validity | ≥ 95% | 80–95% | < 80% |
| SLA Breach | On Track | — | Breached |
| Recon Breaks | 0 | 1–10 | > 10 |

## 🧠 Anomaly Detection Algorithm
Uses the **Interquartile Range (IQR)** method:
- Lower fence = Q1 − 1.5 × IQR
- Upper fence = Q3 + 1.5 × IQR
- Any price outside these bounds is flagged as an anomaly

In a production system, this would be replaced with `sklearn.ensemble.IsolationForest` on real market data.

## 🛠️ Tech Stack
- **React 18** (via CDN — no npm install needed)
- **Recharts** (charts and visualisations)
- **Babel Standalone** (JSX transpilation in-browser)
- **Vanilla CSS** (no framework)

## 📁 Project Structure
```
investment-data-health-monitor/
├── index.html        ← entire app (self-contained)
└── README.md
```

## ⚡ Deploy to GitHub Pages (3 steps)
1. Push this repo to GitHub
2. Go to **Settings → Pages → Source: Deploy from branch → main / root**
3. Visit `https://<your-username>.github.io/Investment-Data-Health-Monitor/`

No build step. No npm. No database. Just static HTML.

## 🔮 Production Roadmap
- [ ] Replace synthetic data with FastAPI + pandas backend
- [ ] Swap JS IQR with `sklearn` Isolation Forest
- [ ] Add Gemini API for real exception summarisation
- [ ] Connect to Snowflake / Databricks for live investment data
- [ ] Add SOP documentation per domain

## 👩‍💻 Author
**Anushree Revankar**  
B.Tech Computer Engineering (Hons. Data Science) — DJSCE Mumbai  
[LinkedIn](https://linkedin.com/in/anushree-revankar) · [GitHub](https://github.com/Anushre2005)
