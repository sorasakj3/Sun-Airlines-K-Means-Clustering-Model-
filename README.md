# Sun-Airlines-K-Means-Clustering-Model-
# ✈️ Customer Segmentation for Sun Country Airlines

This project applied unsupervised learning on flight reservation data to identify key customer segments and develop targeted marketing strategies for Sun Country Airlines. By leveraging K-Means clustering and behavioral analytics, we delivered a data-driven roadmap to increase loyalty program enrollment and customer lifetime value.

---

## Project Goal

To segment over **15,000 customers** using machine learning, identify behavioral patterns in booking, spending, and loyalty engagement, and deliver **cluster-specific marketing recommendations** that improve retention and direct booking.

---

## Dataset Overview

- **Rows**: 15,144
- **Columns**: 90+ (post feature engineering)
- **Selected Variables**:
  - `BaseFareAmt` (normalized spend)
  - `group_size`, `round_trip` (travel pattern)
  - `days_pre_booked`, `BookingChannel`, `TrvldClassOfService`
  - `age_group`, `seasonality_Q1–Q4`
  - `UflyMemberStatus` (binary + elite tier)
- **Missing Values**: All handled with imputation or filtering

---

## Methodology

### Data Preparation
- Dropped unique IDs and low-variance features (`PNRLocatorID`, `uid`)
- Scaled all continuous features using `MinMaxScaler`
- One-hot encoded all categorical columns
- Final shape: `(15,144 rows × 88 features)`

### Clustering Model
- **Algorithm**: `KMeans` from `scikit-learn`
- **Optimization**: Used the **Elbow Method** to determine optimal `k = 5`
- **Clustering basis**: Behavioral features like booking method, spend, class, loyalty status, and booking lead time
- **Cluster distribution**:

- ---

## Cluster Profiles & Insights

### Cluster 0: **The Honeymooners**
- 3,843 passengers
- **Highest avg. base fare**: $333.00
- 100% book through third-party sites
- 0% Ufly enrollment  
**Takeaways**:
- Introduce **joint loyalty accounts for couples**
- Launch **bundle deals** (flight + resort) directly on the SCA website
- Incentivize sign-ups with inflight perks (e.g. free Wi-Fi)

---

### Cluster 1: **Solo Adventurers**
- 2,353 passengers
- Primarily 55+ travelers
- Book via website but only **25% enrolled** in Ufly
- Most travel alone; moderate avg. spend: $271.00  
**Takeaways**:
- Simplify rewards sign-up UX for older travelers
- Promote “Bring a Friend” and solo travel discounts
- Highlight time-saving perks like **expedited security** or **priority luggage**

---

### Cluster 2: **Holiday Honeys**
- 4,127 passengers (**largest segment**)
- Travel spikes in Q4 (winter holidays)
- High First Class usage
- Avg. spend: $311.73  
**Takeaways**:
- Promote **seasonal holiday bundles** and partner hotel points sharing
- Launch “Fly Together Save Together” campaign
- Cross-sell premium seats with early booking bonuses

---

### Cluster 3: **Last-Minute Savers**
- 2,436 passengers
- Book closest to departure date
- Lowest avg. spend: $270.37
- Book mainly one-way; loyalty program **nonexistent**  
**Takeaways**:
- Offer **last-minute web-only promos**
- Create bundles with airport snacks/lounges
- Run "double miles for solo flyers" offer for reward sign-ups

---

### Cluster 4: **Faithful Travelers**
- 2,385 passengers
- 99.9% Ufly members, 45 Elite status
- Highest First Class usage
- Avg. spend close to Cluster 0  
**Takeaways**:
- Add **birthday mailers and physical perks** (e.g. free baggage, priority line)
- Promote a **Sun Airlines credit card** with triple miles on bookings
- Host **elite-only events** to retain high-value flyers

---

##  Key Visuals

-  **Elbow Plot** to determine optimal K
- Average spend per cluster
- Booking channel histograms and pie charts
-  Age group distribution by cluster
- Days pre-booked histograms
- Scatter plots: Spend vs. group size; booking time vs. fare
- Seasonality heatmaps across segments

---

##  Business Impact

Identified high-value segment with **$333+ avg. spend** but **0% loyalty engagement**  
Recommended loyalty UX overhaul for 55+ travelers  
Enabled targeted campaigns by segment, e.g. holiday promos, business-class perks  
Built framework for **data-driven marketing** with clear segment-level KPIs

---

## 🛠️ Tech Stack

- **Python**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **Tools**: Google Colab, Jupyter Notebook
- **ML Techniques**: K-Means, Elbow Method, One-hot Encoding, Data Normalization

---

> Developed as part of the UC Irvine Business Analytics program with a focus on real-world ML-driven marketing strategy.
