![RedBus Data Decode Hackathon Banner](https://datahack-prod.s3.amazonaws.com/tournament_banner_image/redbus_banner.png)

# 🚌✨ RedBus Data Decode: Route-Level Demand Forecasting 2025 ✨🚌

Welcome to the **RedBus Data Decode: Route-Level Demand Forecasting 2025** repository!  
This challenge is your ticket to the world of advanced demand forecasting using real industry data. Make your mark by building data-driven solutions to forecast bus journey demand in India’s largest bus platform!

---

## 🚀 Table of Contents

- [🎯 About the Hackathon](#-about-the-hackathon)
- [🧩 Problem Statement](#-problem-statement)
- [📊 Data Dictionary](#-data-dictionary)
- [🔍 Technical Overview](#-technical-overview)
- [🛠️ Your Task](#-your-task)
- [📏 Evaluation Metric](#-evaluation-metric)
- [🗝️ Data Split & Leaderboard](#-data-split--leaderboard)
- [🌐 External Data Policy](#-external-data-policy)
- [🐍 Modeling Tools](#-modeling-tools)
- [📜 Ethics & Compliance](#-ethics--compliance)
- [🚦 Getting Started](#-getting-started)
- [👥 Team Details](#-team-details)

---

## 🎯 About the Hackathon

Forecasting demand in bus transportation isn’t just about pricing—it powers marketing, discounts, SEO, and more.  
With **less than 20% of bookings made in advance**, predicting demand is both crucial and complex.  
This hackathon challenges you to leverage historical booking and search data, plus allowed external signals, to build a *robust forecasting model*.

---

## 🧩 Problem Statement

- **Goal:**  
  Predict the total number of bus seats booked for each route **15 days before the journey date**.

- **Influencing Factors:**  
  - National & regional holidays
  - Wedding seasons
  - Long weekends
  - School vacations, exam schedules
  - Day-of-week effects
  - Regional diversity: Not all holidays impact every route equally!

- **Example:**  
  For a route from City A to City B with journey date `30-Jan-2025`, forecast the final seat count **on `16-Jan-2025` (15 days prior)**.

---

## 📊 Data Dictionary

Your solution will use the following datasets:

| File                | Columns & Description                                                                                  |
|---------------------|------------------------------------------------------------------------------------------------------|
| **train.csv**       | `doj`: Date of Journey<br>`srcid`: Source City ID<br>`destid`: Destination City ID<br>`final_seatcount`: Total seats booked (Target) |
| **test.csv**        | `route_key`: Unique row ID<br>`doj`: Date of Journey<br>`srcid`, `destid`: City IDs                  |
| **transactions.csv**| `doj`, `doi`: Journey & Issue Date<br>`dbd`: Days Before Departure<br>`srcid`, `destid`: City IDs<br>`srcid_region`, `destid_region`: Regions<br>`srcid_tier`, `destid_tier`: City Tiers<br>`cumsum_seatcount`, `cumsum_searchcount`: Cumulative metrics |
| **submission_file.csv** | `route_key`: Unique row ID<br>`final_seatcount`: Seats forecasted for journey date                    |

---

## 🔍 Technical Overview

This repository centers on the notebook [`533.4200905274.ipynb`](./533.4200905274.ipynb), which contains the main solution pipeline:

### 📦 Libraries Used

- **Pandas**: Data loading, manipulation, and merging.
- **NumPy**: Numerical operations & efficient array handling.
- **Scikit-learn**: Data preprocessing, feature engineering, model selection, and evaluation (RMSE).
- **LightGBM / XGBoost / CatBoost**: Gradient boosting algorithms for regression tasks.
- **Matplotlib/Seaborn**: Data visualization for EDA and feature analysis.

### 🏗️ Solution Structure

1. **Problem Statement & EDA**  
   - Exploratory Data Analysis: uncover trends, outliers, and demand drivers.
   - Insights into holiday effects, booking windows, and route popularity.

2. **Feature Engineering**  
   - Calendar features: extracting weekends, holidays, school vacations.
   - Booking behavior: cumulative seats/searches, days-before-departure, route popularity.
   - Regional and tier-based segmentation.

3. **Modeling**  
   - Regression models (LightGBM, XGBoost, CatBoost).
   - Cross-validation for robust performance.
   - Hyperparameter tuning and ensemble strategies.

4. **Prediction Pipeline**  
   - Preprocessing test data to match feature space.
   - Generating predictions for the 15-day-ahead forecast.

5. **Submission & Evaluation**  
   - Formatting results as per `submission_file.csv`.
   - RMSE calculation for leaderboard tracking.

### 💡 Unique Approaches

- **Calendar-aware features:** Integration of external holiday/event calendars to boost accuracy.
- **Cumulative metrics:** Using `cumsum_seatcount` and `cumsum_searchcount` to capture booking/search trends.
- **Segmented modeling:** Considering region and tier to differentiate routes.
- **Automated feature selection:** Importance ranking to reduce overfitting.

---

## 🛠️ Your Task

- **Predict:** `final_seatcount` for each route, 15 days ahead of the journey date.
- **Use:** Historical and allowed external data only.

---

## 📏 Evaluation Metric

- **Metric:** Root Mean Squared Error (RMSE)
- **Leaderboard:**  
  - Public (30% test) for real-time feedback  
  - Private (70% test) for final ranking

```
Sample Scores:
Public Score: 567.0482855914
Private Score: 533.4200905274
```

---

## 🗝️ Data Split & Leaderboard

- **Public Data (30%)**: Initial evaluation, real-time leaderboard
- **Private Data (70%)**: Final evaluation, ranks revealed after competition

---

## 🌐 External Data Policy

🚫 **Prohibited:**
- Other seat booking datasets/aggregators
- Publicly available similar datasets

✅ **Allowed:**
- External holiday/event calendars (regional/national)
- Public data relevant to the problem statement

---

## 🐍 Modeling Tools

- **Language:** Python 3.8+
- **Libraries:** Any open-source Python data science library/framework

---

## 📜 Ethics & Compliance

- ❌ No plagiarism or unethical behavior
- ✔️ Fair play is a must

---

## 🚦 Getting Started

1. **Clone this repo:**
   ```bash
   git clone https://github.com/KishoreMuruganantham/RedBus-Data-Decode-Route-Level-Demand-Forecasting-2025.git
   cd RedBus-Data-Decode-Route-Level-Demand-Forecasting-2025
   ```

2. **Setup environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Place datasets in `/data` folder.**

4. **Dive into [`533.4200905274.ipynb`](./533.4200905274.ipynb):**  
   Explore the pipeline and start innovating!

---

## 👥 Team Details

- Kishore Muruganantham — [GitHub](https://github.com/KishoreMuruganantham)
- Mugundhan Y — [GitHub](https://github.com/MugundhanY)
- Mukundh A P — [GitHub](https://github.com/MukundhArul)
- Prince Raj J — [GitHub](https://github.com/the-ai-developer)

---

## 🎉 Final Touch: Happy Forecasting! 🎉

May your models be accurate and your features insightful.
Good luck, and let your data science journey take you places! 🚍📈🌟
