# DataCo Supply Chain Analytics & Predictive ML

## Business Analytics and Predictive Risk Case Study

An end-to-end supply chain analytics project connecting operational evidence, commercial performance, predictive risk modeling, Power BI decision support, Streamlit deployment, and scenario-based financial analysis.

### Business Question

**Where is delivery risk concentrated, what commercial patterns matter, and how can high-risk orders be identified before shipment execution?**

---

## Executive Results

| KPI | Result |
|---|---:|
| Total Sales | $36.78M |
| Total Profit | $3.97M |
| Profit Margin | 10.78% |
| Order Items | 180,519 |
| Late Delivery Rate | 54.83% |
| Model ROC-AUC | 74.2% |
| Estimated Scenario Net Savings | $153,080 |

---

## Key Business Findings

- Late delivery affects **54.83% of order items**, making service reliability a material operational concern.
- **First Class** has the highest observed historical late-delivery rate at **95.32%**.
- **Second Class** follows at **76.63%**.
- Average scheduled shipping duration is **2.93 days**, compared with **3.50 days actual shipping duration**.
- **Central Africa, South Asia, and East Africa** appear among the highest late-delivery risk concentrations in the dashboard.
- **Europe** is the highest-sales market.
- **Fishing** is the leading sales category.
- **Consumer** is the largest customer segment by sales and profit.
- Average profit declines as discount levels increase across the analyzed discount bands.

Historical delivery rates are used as descriptive evidence and are **not hard-coded prediction rules**.

---

## Predictive Analytics

The predictive model estimates late-delivery risk at the **order-placement stage**.

### Model

**Gradient Boosting Classification**

### Model Inputs

- Transaction Type
- Days for Shipment (Scheduled)
- Shipping Mode
- Order Item Quantity
- Sales
- Order Item Discount
- Category Name
- Department Name
- Order Region

Post-shipment outcome fields are excluded from the predictive feature set to preserve the order-placement prediction boundary.

### Model Evaluation

| Metric | Result |
|---|---:|
| Accuracy | 69.7% |
| Precision | 84.3% |
| Recall | 55.0% |
| F1 Score | 66.5% |
| ROC-AUC | 74.2% |
| 5-Fold CV Accuracy | 69.5% |

These are executed holdout and cross-validation results and are not guarantees of future production performance.

---

## Decision Support

The project converts prediction into an operational workflow:

**Order → Score → Prioritize → Review → Intervene → Measure**

The Streamlit application accepts order-time inputs, returns late-delivery probability, assigns a presentation-level risk band, recommends an operational action, and provides scenario-based financial context.

### Risk Bands

| Probability | Risk |
|---|---|
| Below 40% | Low Risk |
| 40%–69.9% | Medium Risk |
| 70%+ | High Risk |

---

## Financial Scenario

The project includes a scenario analysis using:

- **$20 late-delivery penalty**
- **$5 expedite cost**

The executed scenario estimates:

**$153,080 net scenario savings**

with a **38.66% scenario ROI**.

These are assumption-based scenario estimates, not realized business savings.

---

## Power BI Dashboard

The final Power BI dashboard provides four management views:

1. **Executive Overview**
   - Sales
   - Profit
   - Profit Margin
   - Order Volume
   - Late Delivery
   - Market and Customer Segment performance

2. **Delivery & Operational Risk**
   - Shipping Mode
   - Market
   - Region
   - Delivery Status
   - Scheduled vs Actual Shipping Duration

3. **Commercial Performance**
   - Market
   - Category
   - Customer Segment
   - Discount
   - Shipping Mode profitability

4. **Executive Recommendations**
   - Delivery risk actions
   - Shipping strategy
   - Commercial discipline
   - Predictive operations
   - Financial prioritization

---

## Project Architecture

```text
DataCo Supply Chain Dataset
            ↓
Data Audit & Cleaning
            ↓
Business & Commercial Analysis
            ↓
Predictive ML
            ↓
Model Evaluation
       ↙         ↘
Power BI       Streamlit
Dashboard      Risk Predictor
       ↘         ↙
   Decision Support
            ↓
Scenario Financial Analysis
```

---

## Repository Structure

```text
DataCo_Supply_Chain_Analytics/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   ├── supply_chain_model.pkl
│   ├── model_features.pkl
│   ├── model_metrics.json
│   └── business_config.json
│
├── data/
│   ├── raw/
│   │   └── README.md
│   └── processed/
│       └── README.md
│
├── notebooks/
│   └── DataCo_Supply_Chain_Analytics_and_ML_FINAL.ipynb
│
├── powerbi/
│   └── DataCo_Supply_Chain_Flagship_v4.pbix
│
├── report/
│   └── DataCo_Supply_Chain_Flagship_Project_Report.pdf
│
├── .gitignore
└── README.md
```

---

## Project Evidence

| Layer | Artifact |
|---|---|
| Analytics & ML | Jupyter Notebook |
| Decision Dashboard | Power BI |
| Risk Prediction | Streamlit |
| Model Pipeline | `supply_chain_model.pkl` |
| Feature Schema | `model_features.pkl` |
| Model Metrics | `model_metrics.json` |
| Scenario Configuration | `business_config.json` |
| Case Study | Final PDF Report |

---

## Data Source

**DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS**

Public Kaggle dataset:

https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

The raw source file is documented in `data/raw/README.md`.

The raw and processed CSV files are not committed to the repository because of file-size constraints.

---

## Analytical Integrity

- Historical relationships are treated as descriptive evidence, not causal effects.
- Post-shipment outcome fields are excluded from predictive inputs.
- Model performance is reported from the executed evaluation workflow.
- Risk bands are presentation-level probability thresholds.
- Financial results are scenario estimates based on explicit assumptions.
- Scenario savings are not presented as realized business performance.

---

## Author

**Vipulchandra Prajapati**  
Business Analyst  
vipcogent@gmail.com
