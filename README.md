# 🏠 Real Estate Price Prediction

> **Type:** Predictive Modelling · Statistical Feature Selection · Regression Analysis
>
> **Tools:** Python · Pandas · Statsmodels · Scikit-learn · Seaborn · Matplotlib
>
> **Dataset:** [Real Estate Price Prediction](https://www.kaggle.com/datasets/quantbruce/real-estate-price-prediction)

---

## 🏢 Business Problem

Real estate buyers, sellers, and agents lack a transparent, **data-driven method to estimate fair property prices**. The question:

> *Which property attributes actually drive price per unit area — and which are noise?*

---

## 📐 Approach

| Step | What I Did |
|------|-----------|
| **EDA** | Pair plots across all 6 features to assess linear relationships with price visually |
| **Full OLS Model** | Fitted regression with all 6 features using `statsmodels` |
| **Feature Selection** | Used **p-value hypothesis testing** (α = 0.05) — dropped `longitude` (p > 0.05, not significant) |
| **Refined Model** | Refit OLS with 5 significant predictors only |
| **Residual Validation** | Plotted residual distribution — confirmed normality (OLS assumption check) |
| **Error Metric** | Computed RMSE to quantify prediction accuracy |

---

## 📊 Key Findings

**Final Model:**
```
Price = −15,960
      + 5.13  × (transaction date)
      − 0.27  × (house age)
      − 0.004 × (distance to MRT station)
      + 1.14  × (number of nearby convenience stores)
      + 226.88× (latitude)
```

- All 5 retained features statistically significant (p < 0.05)
- **Longitude dropped** — p > 0.05, no meaningful relationship with price
- **MRT distance** and **nearby convenience stores** were strongest location-based price drivers
- Residuals normally distributed with mean ≈ 0 → OLS assumptions satisfied

---

## 💡 Business Recommendation

> Location dominates pricing — proximity to public transit and retail density matter more than property age. Agents and developers should weight location scoring heavily when estimating or justifying valuations.

---

## 📁 Repository Structure

```
real-estate-price-prediction/
│
├── notebook/
│   └── multiple-linear-regression.ipynb
│
├── images/
│   ├── pairplot.png
│   └── residual_plot.png
│
└── README.md
```

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/real-estate-price-prediction.git

# Install dependencies
pip install pandas numpy statsmodels matplotlib seaborn

# Run the notebook
jupyter notebook notebook/multiple-linear-regression.ipynb
```

> 📎 Dataset: [Real Estate Price Prediction on Kaggle](https://www.kaggle.com/datasets/quantbruce/real-estate-price-prediction)
