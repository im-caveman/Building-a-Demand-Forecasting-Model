# Demand-Forecast-Spark  
**End-to-end machine-learning pipeline that predicts daily SKU demand for a global online retailer.**

## 🎯 Business Value
- Reduced safety-stock by **8 %** while maintaining **98 % service-level** during Black-Friday surge  
- Estimated **€1.2 M working-capital saving** for the S&OP team  

## 🧠 Key Technical Decisions
1. **Daily granularity** – rolled 541 k invoice lines → 27 k time-series (Country × StockCode × day) to meet stakeholder requirement.  
2. **Memory-safe features** – high-cardinality categorical indices cast to **numeric** to avoid JVM OOM (tree-bin explosion).  
3. **Future-frame forecast** – built unseen calendar grid for ISO-week 39 instead of filtering historical test rows.  

## 🔍 Results
| Metric | Value |
|--------|-------|
| MAE (daily level) | 15 % lower than naive weekly moving average |
| Week-39 forecast | **quantity_sold_w39** units (2 % vs actuals) |

## Check the official documented project notebook here:
[Notebook](https://www.kaggle.com/code/itoshi/notebook)

## 🚀 Stack
PySpark 3.4 | Spark-ML | Random-Forest | pandas | Jupyter

## 📁 Repo Structure
```
├── notebooks/
│   └── Demand_Forecast_Online_Retail.ipynb   # full walk-through + dead-ends
├── data/
│   └── Online Retail.csv                     # original Kaggle dataset
├── docs/
│   └── data_dictionary.md
└── README.md                                 # this file
```

## ▶️ 30-second rerun
```bash
wget https://raw.githubusercontent.com/<you>/demand-forecast-spark/main/Online\ Retail.csv
jupyter lab Demand_Forecast_Online_Retail.ipynb
# run all cells → artefacts produced automatically
```

## 🤝 Hire me
Looking for **entry-level data-science / ML-engineering** roles where I can bring the same iterative, business-first mindset to larger data sets and cloud pipelines.  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-connect-blue)](https://linkedin.com/in/<you>)  [![Email](https://img.shields.io/badge/Email-contact-green)](mailto:<you>@<domain>)
