# 📱 Mobile Game Monetization Dashboard (2025)

A Power BI dashboard project analyzing **in-app purchase monetization** for a mobile game dataset.  
The focus is on **core monetization KPIs**, **spending segments**, **device impact**, and **country-level revenue distribution**.

---

## 🎯 Project Goal

- Build a clean, analysis-ready dataset
- Calculate **core monetization metrics** (Total Revenue, Conversion Rate, ARPU, ARPPU)
- Visualize monetization performance with a clear, stakeholder-friendly dashboard
- Provide short **insights & recommendations** based on the results

---

## 🧰 Tech Stack

- **Google BigQuery (SQL)** → data cleaning + metric calculations  
- **Power BI** → dashboard design & visuals  
- **CSV export** → used for importing into Power BI (when direct connection was not available)

---

## 📦 Dataset

- Table (raw): `mobile_game_inapp_purchases`
- Table (clean): `mobile_game_inapp_purchases_clean`
- Key fields: `UserID`, `InAppPurchaseAmount`, `SpendingSegment`, `Country`, `Device`, `SessionCount`, `LastPurchaseDate`, etc.

> **Note:** Currency is assumed to be **USD** based on the dataset.

---

## 🧼 Data Cleaning Summary (BigQuery)

Main cleaning actions applied:

- ✅ **Type casting**
  - `Age` → `INT64`
- ✅ **Missing value handling**
  - `Gender`, `Country`, `Device` → filled with `"Unknown"` where NULL
- ✅ **Date formatting**
  - ensured `LastPurchaseDate` is stored/handled as a date-friendly format
- ✅ **Feature engineering**
  - created a purchase flag: `has_purchase_data`  
    - `TRUE` if `InAppPurchaseAmount` is not NULL, else `FALSE`

---

## 📊 Core Metrics (Overall)

From the cleaned dataset:

- 👥 **Total Users:** 3,024  
- 💳 **Paying Users:** 2,888  
- 🔁 **Conversion Rate (Paying / Total):** 95.5%  
- 💰 **Total Revenue:** **$296.26K**  
- 📈 **ARPU:** **$97.97**  
- 📈 **ARPPU:** **$102.58**

### What do ARPU / ARPPU mean?
- **ARPU (Average Revenue Per User)**  
  Total Revenue / Total Users → average revenue across *all* users.
- **ARPPU (Average Revenue Per Paying User)**  
  Total Revenue / Paying Users → average revenue for *only paying* users.

---

## 🧠 Spending Segments

Segments used in the dataset:
- 🐋 **Whale** = heavy spenders (typically high spend)
- 🐬 **Dolphin** = moderate spenders
- 🐟 **Minnow** = low spenders

---

## 📌 Dashboard Highlights (Power BI)

This report includes:

- 📌 **KPI Cards:** Total Users, Paying Users, Conversion Rate, Total Revenue, ARPU, ARPPU  
- 🐋 **Revenue by Spending Segment** (high concentration expected in Whales)
- 👥 **User Count by Spending Segment** (user base distribution)
- 🍩 **Paying vs Non-Paying Users** (share)
- 📱 **Revenue Share by Device** (Android vs iOS)
- 🗺️ **Revenue by Country (Top 10)** using map visualization
- 🧾 **Summary & Recommendations** page

> Screenshots are stored under the **`/visuals`** folder (not embedded into this README).

