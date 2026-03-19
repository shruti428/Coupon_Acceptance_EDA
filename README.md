# Coupon Acceptance EDA

This project analyzes survey data collected via Amazon Mechanical Turk to understand what factors influence a driver's decision to accept a coupon delivered to their cell phone while driving.

The dataset includes five coupon types: bars, coffee houses, carry out & take away, inexpensive restaurants (under $20), and mid-range restaurants ($20–$50).

---

## Data & Methodology

| Attribute | Details |
|---|---|
| **Source** | UCI Machine Learning Repository (Amazon Mechanical Turk survey) |
| **Records** | 12,684 driving scenarios |
| **Features** | 26 attributes (driver demographics, weather, time of day, passenger type, coupon type) |
| **Target Variable** | Coupon accepted (Y=1) or rejected (Y=0) |
| **Missing Data** | `car` column dropped (99% missing); remaining missing categoricals filled with `"Missing"` |

---

## Key Finding: Overall Acceptance Rate

> **56.8%** of all coupons were accepted overall.

Acceptance rates vary by coupon type, driver demographics, and other factors, suggesting that **targeted delivery can dramatically improve acceptance rates**.

---

## Acceptance Rates by Coupon Type

### Bar Coupons

Overall acceptance rate: **41%**.

However, certain segments are far more likely to accept:

- Drivers who visit bars **3+ times/month**
- Drivers **over age 25** who visit bars **1+ times/month**
- Drivers who visit bars **1+ times/month** with **no kid passengers** and a **non-farming occupation**

> **Key Takeaway:** Bar coupons should be targeted at frequent bar-goers (3+ visits/month) who are over 25 and traveling without children.

---

### Carry Out & Take Away Coupons

Overall acceptance rate: **~74%** — the highest of all coupon types and the easiest win.

**Factors that increase acceptance:**

| Factor | Detail |
|---|---|
| Time of day | 2PM and 6PM see the highest acceptance (~83–87%); 7AM is lowest (~65%) |
| Weather | Sunny conditions drive more acceptance (~76%) vs. rainy (~61%) |
| Expiration window | 1-day coupons outperform 2-hour coupons (78% vs. 66%) |
| Destination | Drivers heading home or with no urgent destination are more receptive |

**Factors that decrease acceptance:**

- Drivers heading to work
- Rainy or snowy weather
- Graduate degree holders accept less frequently than those with lower education levels

> **Key Takeaway:** Carry-out coupons are most effective when delivered mid-afternoon or early evening on sunny days, to drivers without a time-sensitive destination, with at least a 1-day expiration window.

---

## General Recommendations

1. **Time carry-out coupon delivery** — Send around 2PM and 6PM for maximum impact. Avoid morning delivery.
2. **Extend expiration windows** — 1-day coupons consistently outperform 2-hour coupons. Default to longer windows where operationally feasible.
3. **Weather-aware delivery** — Sunny-day delivery yields measurably better acceptance.
4. **Segment bar coupon targeting** — Prioritize frequent bar-goers (3+ visits/month) who are over 25 and traveling without children. delivery — Limit bar coupons to drivers who visit bars frequently and are not traveling with children.
5. Use modeling approaches to identify strong predictors of acceptance rate

## Repository Contents
```
├── Coupon_Acceptance_EDA.ipynb   # Jupyter notebook with full analysis
├── data/
│   └── coupons.csv               # Raw survey data
└── README.md                     # Project overview
```

