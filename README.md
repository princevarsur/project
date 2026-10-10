# Market Surveillance & Compliance Reporting System

A Python and Power BI–based market surveillance and compliance analytics system designed to review equity trading activity, identify potential regulatory risk signals, and produce explainable, audit-ready reporting aligned with real-world compliance workflows.

---

## 1. Business & Regulatory Context

Investment firms operating in regulated markets are required to continuously monitor trading activity to detect potential market abuse, including wash trading, spoofing, and other manipulative behaviors. Compliance teams must not only identify anomalous activity but also maintain transparent, defensible documentation suitable for review by legal teams and regulators.

This project simulates the end-to-end workflow of a **Compliance Analyst**, from raw trading data ingestion to structured surveillance analysis and regulatory-style reporting.

---

## 2. Project Objectives

- Review message-level equity trading activity
- Detect potential regulatory risk signals using explainable, rule-based logic
- Aggregate surveillance findings into prioritized compliance risk scores
- Produce audit-ready datasets and interactive dashboards for compliance review
- Demonstrate quantitative and qualitative analysis in a regulatory context

---

## 3. Datasets Used

### 3.1 LOBSTER Market Data
- Message-level trading events (order submissions, cancellations, executions)
- Order book snapshots (top-of-book depth)
- Instruments analyzed:
  - AAPL
  - AMZN
  - GOOG
  - INTC
  - MSFT

**Source:**  
https://lobsterdata.com/info/DataSamples.php

---

## 4. Project Architecture

## 4. Project Architecture


Raw Market Data

│
▼
data/raw/

└── Raw LOBSTER message and order book CSVs

│
▼
data/processed/

└── Cleaned trades, cancellations, engineered features, and risk metrics

│
▼
notebooks/01_ingestion.ipynb

└── Data ingestion, normalization, and timestamp alignment

│
▼
notebooks/02_feature_engineering.ipynb

└── Feature engineering for order flow, volatility, and bid–ask dynamics

│
▼
notebooks/03_surveillance_rules.ipynb

└── Rule-based surveillance detection
(spoofing, layering, wash trading proxies)

│
▼
notebooks/04_risk_scoring.ipynb

└── Aggregation of surveillance signals into entity-level risk profiles

│
▼
src/surveillance_utils.py

└── Modular, reusable logic for surveillance rules and compliance KPIs

│
▼
powerbi/compliance_dashboard.pbix

└── Executive-level compliance and regulatory reporting dashboards

---

## 5. Data Pipeline Overview

1. Ingest raw message and order book data
2. Normalize timestamps, prices, directions, and event types
3. Engineer order- and trade-level behavioral features
4. Apply rule-based surveillance detection logic
5. Aggregate signals into composite compliance risk scores
6. Export structured datasets for Power BI reporting

---

## 6. Surveillance Rules Implemented

The following regulatory surveillance signals are implemented using transparent, threshold-based logic commonly used in compliance monitoring.

### 6.1 Wash Trading Proxies
- Rapid directional reversals
- Opposite-side executions within short time windows

### 6.2 Spoofing Indicators
- Excessive order cancellations
- High order-to-trade ratios
- Short-lived large orders

### 6.3 Abnormal Trading Activity
- Trade size outliers using Z-score analysis
- Volume concentration anomalies

### 6.4 End-of-Day Price Pressure
- Elevated trading activity near market close
- Potential closing price manipulation signals

All rules are explainable and suitable for audit review.

---

## 7. Risk Scoring Framework

Surveillance signals are aggregated into a **composite compliance risk score (0–100)** to prioritize review and escalation.

| Signal Type | Weight |
|------------|--------|
| Wash trading indicators | 30% |
| Abnormal trade size | 25% |
| End-of-day activity | 15% |
| Cancellation intensity | 30% |

Higher scores indicate elevated compliance review priority.

---

## 8. Reporting & Dashboards (Power BI)

The Power BI report includes the following views:

### 8.1 Compliance Overview
- Total trades reviewed
- Flagged activity volume
- Risk score distribution
- High-risk instruments

### 8.2 Surveillance Monitoring
- Wash trade trends over time
- Cancellation rate by instrument
- Abnormal trade size detection

### 8.3 Instrument Drill-Down
- Trade-level details
- Triggered surveillance rules
- Time-based analysis

### 8.4 Audit & Explainability
- Rule triggered per alert
- Threshold breached
- Supporting quantitative metrics

---

## 9. Key Outputs

- Clean, audit-ready surveillance datasets
- Compliance risk scoring tables
- Interactive Power BI dashboards
- Explainable rule-based flagging logic

---

## 10. Technologies Used

- Python (Pandas, NumPy)
- Power BI
- Jupyter Notebook

---

## 11. Limitations

- Public datasets do not include trader identifiers; analysis is performed at instrument and order-behavior levels
- Surveillance logic is rule-based rather than predictive
- Dataset represents a limited historical time window

---

## 12. Key Skills Demonstrated

- Trade surveillance & compliance analytics
- Regulatory risk identification
- Explainable, audit-ready reporting
- Quantitative and qualitative analysis
- Stakeholder-oriented dashboarding
