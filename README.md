Customer Lifetime Value (CLV) & Revenue Segmentation Analysis

🎯 Project Overview

This project analyzes e-commerce transaction data to understand customer purchasing behavior, identify high-value customers, and segment them using RFM (Recency, Frequency, Monetary) analysis. The goal is to derive actionable insights to improve customer retention and maximize revenue.

---

🧠 Problem Statement

Analyze customer purchase data to identify high-value customers, segment them based on their contribution to revenue, and provide business recommendations to improve retention and overall profitability.

---

🎯 Objectives

- Identify high-value customers
- Understand customer purchase patterns
- Perform RFM-based segmentation
- Analyze revenue distribution
- Provide data-driven business recommendations

---

📂 Dataset

- Online Retail Dataset (UK-based e-commerce transactions)
- ~500K+ rows of transaction data
- Features include:
  - CustomerID
  - InvoiceNo
  - Quantity
  - UnitPrice
  - InvoiceDate
  - Country

---

🧹 Data Cleaning

- Removed missing "CustomerID" values
- Excluded cancelled transactions (InvoiceNo starting with 'C')
- Filtered out negative and zero values for "Quantity" and "UnitPrice"
- Created a new column:
  - "Revenue = Quantity × UnitPrice"

🔍 Insight

A significant portion of raw data contained invalid or incomplete records. Cleaning ensured that analysis reflects accurate customer behavior.

---

🧠 Feature Engineering

- Aggregated transaction data at customer level
- Created RFM metrics:
  - Recency → Days since last purchase
  - Frequency → Number of orders
  - Monetary → Total spend

---

📊 Analysis & Visualizations

- Customer spending distribution
- Frequency vs Monetary relationship
- Recency vs Monetary behavior
- Customer segmentation (Low, Medium, High)
- Revenue contribution by segment

---

🧮 SQL-Based Analysis

Used SQL concepts to validate aggregation logic and extract key metrics.

-- Total Revenue
SELECT SUM(Quantity * UnitPrice) AS total_revenue FROM data;

-- Top Customers
SELECT CustomerID, SUM(Quantity * UnitPrice) AS revenue
FROM data
GROUP BY CustomerID
ORDER BY revenue DESC
LIMIT 10;

-- Customer Order Frequency
SELECT CustomerID, COUNT(DISTINCT InvoiceNo) AS total_orders
FROM data
GROUP BY CustomerID;

---

🔍 Key Insights

- Revenue is highly concentrated among a small group of high-value customers
- Majority of customers are low-frequency buyers
- Customers with high recency are at risk of churn
- High-value customers show strong engagement and repeat behavior
- Customer value distribution follows a Pareto-like pattern

---

📈 Advanced Insight

Top 20% of customers contribute a significant portion of total revenue, confirming the Pareto principle in customer behavior.

---

💡 Business Recommendations

- Retain high-value customers through loyalty programs and personalized offers
- Convert one-time buyers into repeat customers
- Re-engage inactive customers using targeted campaigns
- Increase purchase frequency of medium-value customers
- Use segmentation for targeted and efficient marketing

---

🛠️ Tools & Technologies

- Python (Pandas, Matplotlib, Seaborn)
- SQL (aggregation, filtering, grouping)
- Jupyter Notebook

---

🚀 Conclusion

Customer revenue is highly skewed, with a small segment driving most of the business. Improving retention and increasing repeat purchases can significantly enhance profitability.

---

👤 Author

Shivam Kumar
