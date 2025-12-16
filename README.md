# DIP-2024-Hackathon---Book-of-Personas
Mini-hackathon for data science interns in the 2024 BPI Data Science Internship Program.

# BPIdex 📊  
Customer Segmentation, Lifetime Value & Persona Generation using Banking Data

BPIdex is a data-driven customer profiling and segmentation project developed for a hackathon. It transforms raw banking transaction, demographic, and psychographic data into actionable customer personas using RFM analysis, Gamma–Gamma modeling, and clustering techniques.

“Gotta know them all!”

---

## 👥 Team
- Lion De Leon  
- Lorenzo Divina  
- Isaiah Mariano  

---

## 🧠 Project Motivation
With over 11 million customers, understanding individual behavior is essential to building personalized financial products and long-term customer relationships.

BPIdex aims to:
- Understand customer diversity
- Convert data into insights
- Enable personalized engagement
- Support data-driven banking strategies

---

## 🗂️ Dataset

### 1. Demographics Dataset
- Age  
- Gender  
- Marital Status  
- Subsegment (Social Class)  
- Customer Tenure  
- Customer ID  

### 2. Psychographics Dataset
Interest tiers (S, A, B, No Data):
- Food Lover
- Fashionista
- Sports Enthusiast
- Traveler
- Book Lover
- Movie Lover
- Coffee Lover
- Tech Geek
- Gamer
- Music Lover

### 3. Credit Transactions Dataset
- Merchant group & name  
- Transaction amount  
- Transaction date  
- Channel (physical / online)  
- Location (PH / foreign)  

---

## 🛠️ Data Processing & Feature Engineering

### Demographics
- Numerical variables transformed into categorical bins:
  - Age: 0–30, 31–39, 40–49, 50–59, 60+
  - Tenure: 0–6, 7–12, 13+ years

### Psychographics
- Interests grouped into general lifestyle categories:
  - Food
  - Fashion
  - Active Living
  - Lifestyle
  - Technology
- Encoding:
  - S & A tiers → 1
  - B & No Data → 0

### Transactions
- Aggregated at the customer level
- Used for RFM and Gamma–Gamma modeling

---

## 📈 RFM Analysis

Each customer is scored using:
- Recency (R): Days since last transaction
- Frequency (F): Number of transactions
- Monetary (M): Total transaction value

### RFM Scoring
- Each metric divided into quartiles (1–4)
- Interpretation:
  - 4 → Best-performing customers
  - 1 → Lowest-performing customers

Weighted RFM scores are later used to:
- Grade clusters
- Support persona valuation

---

## 💰 Gamma–Gamma Model (Customer Monetary Value)

To enhance monetary analysis, BPIdex incorporates the Gamma–Gamma model, commonly used in Customer Lifetime Value (CLV) estimation.

### Purpose
The Gamma–Gamma model estimates a customer’s expected average transaction value under the assumptions that:
- Transaction frequency and monetary value are independent
- Customers with more transactions provide more reliable monetary estimates

### Inputs
- Average monetary value per customer
- Transaction frequency
- Positive monetary values only

### Outputs
- Expected Average Monetary Value
- Used as a refined input for:
  - Lifetime Value (LVL)
  - Profitability metrics
  - Persona ranking and targeting

This improves upon raw monetary totals by stabilizing estimates for customers with fewer transactions.

---

## 🤖 Modeling & Clustering
- Clustering Algorithm: K-Modes  
- Number of Clusters: 6  
- Features Used:
  - Demographics
  - Psychographics
  - RFM scores
  - Gamma–Gamma–derived monetary estimates

### Cluster Grading
Clusters are graded using weighted RFM averages:

| Grade | Weighted Score |
|------|----------------|
| A    | ≥ 3.50 |
| B+   | 3.00 – 3.49 |
| B    | 2.50 – 2.99 |
| C+   | 2.00 – 2.49 |
| C    | 1.50 – 1.99 |
| F    | ≤ 1.49 |

---

## 👤 Customer Personas

Clusters are translated into human-centered personas:
- Balanced Buff – The Jack of All Trades  
- Food Fanatic – Indulges in Culinary Delights  
- Digital Diner – The Tech-Savvy Foodie  
- Media Maven – The Techie Adventurer  
- Active Adventurer – The Thrill-Seeker  
- Fashion Foodie – The Flamboyant Connoisseur  

Each persona includes:
- Demographics and psychographics
- RFM grades
- Gamma–Gamma–informed Lifetime Value (LVL)
- Holding Probability (HP)
- Profitability insights
- Preferred and unpreferred banking products

See Booklet of Personas.pdf for full persona breakdowns.

---

## 🎯 Business Applications
BPIdex supports:
- Personalized product recommendations
- Customer retention and churn prevention
- Loyalty programs for high-value customers
- Reactivation of low-recency users
- Profit optimization using CLV insights

Example initiatives:
- HP Up – Increase holding probability
- Nugget – Retain high-value customers
- Rare Candy – Boost low lifetime value segments
- Revive – Improve recency scores
- Potion – Increase monetary contribution

---

## ⚠️ Limitations
- Limited timeframe and dataset size
- Short-term transaction history
- Simplified psychographic labeling
- Gamma–Gamma assumes independence between frequency and monetary value

---

## 🚀 Future Improvements
- Integrate BG/NBD + Gamma–Gamma for full CLV prediction
- Add churn prediction models
- Use real-time transaction streams
- Expand psychographic data sources
- Validate personas with supervised learning

---

## 📜 License
This project was created for educational and hackathon purposes.  
All data is assumed to be anonymized and non-production.
