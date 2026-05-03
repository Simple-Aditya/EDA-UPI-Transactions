# 📊 EDA — UPI Transactions 2024

Exploratory Data Analysis on a synthetically generated dataset of **250,000 UPI transactions** from 2024, covering payment behaviour, fraud patterns, bank performance, network reliability, and more.

---

## 📌 About the Project

UPI (Unified Payments Interface) is India's real-time payment system developed by NPCI, enabling instant bank-to-bank transfers via mobile. This project digs into a randomly generated UPI transactions dataset to uncover patterns across transaction types, merchant categories, age groups, device usage, fraud trends, and time-based behaviour — using Python-based EDA.

> ⚠️ **Disclaimer:** The dataset (`upi_transactions_2024.csv`) is synthetically generated and sourced from Kaggle. It does not represent real transaction records and is used purely for learning and analytical purposes.

---

## 📁 Repository Structure

```
EDA-UPI-Transactions/
│
├── eda-upi-transactions.ipynb   # Jupyter Notebook with full EDA
└── README.md
```

---

## 🗂️ Dataset Overview

- **Records:** 250,000 transactions
- **Source:** [Kaggle — UPI Transactions 2024 Dataset](https://www.kaggle.com/datasets)
- **Period:** Full year 2024

### Columns

| # | Column | Description |
|---|--------|-------------|
| 1 | `transaction id` | Unique identifier for each transaction |
| 2 | `timestamp` | Date and time of the transaction |
| 3 | `transaction type` | P2P, P2M, Bill Payment, or Recharge |
| 4 | `merchant_category` | Type of merchant (Grocery, Food, Shopping, etc.) |
| 5 | `amount (INR)` | Transaction value in Indian Rupees |
| 6 | `transaction_status` | SUCCESS or FAILED |
| 7 | `sender_age_group` | Age group of the sender (18-25, 26-35, 36-45, 46-55, 56+) |
| 8 | `receiver_age_group` | Age group of the receiver |
| 9 | `sender_state` | Indian state from which payment was initiated |
| 10 | `sender_bank` | Bank used by the sender |
| 11 | `receiver_bank` | Bank receiving the payment |
| 12 | `device_type` | Android, iOS, or Web |
| 13 | `network_type` | Network used (3G, 4G, 5G) |
| 14 | `fraud_flag` | Whether the transaction is flagged as fraudulent |
| 15 | `hour_of_day` | Hour at which payment was made (0–23) |
| 16 | `day_of_week` | Day on which the payment was made |
| 17 | `is_weekend` | Whether the transaction occurred on a weekend |

---

## 🔍 Analysis Structure

### 🧹 Data Cleaning & Preprocessing
- Checked for null values and duplicates
- Converted `timestamp` from object to `datetime`
- Explored unique values and data types across all columns

### 📊 Univariate Analysis

| Feature | Finding |
|---------|---------|
| Transaction Type | P2P dominates, followed by P2M |
| Merchant Category | Grocery and Food are the top categories; Education and Healthcare are the least |
| Amount (INR) | Highly left-skewed — 75% of transactions are below ₹1,600 |
| Sender Age Group | 26–35 age group is the most active |
| Receiver Age Group | Same — 26–35 leads |
| Transaction Status | ~5% of all transactions fail |
| Device Type | Android > iOS > Web |
| Fraud Flag | Only 0.19% of transactions are flagged as fraud |
| Day of Week | Transactions are fairly consistent; Sunday and Monday see a slight spike |

### 📈 Bivariate Analysis

| Question | Finding |
|---------|---------|
| Transaction volume/value over time | Consistent — 600–770 transactions/day; ₹800K–₹1.1M value/day |
| Frauds over time | Steady, ranging 0–6 per day with no sudden spike |
| Merchant volume vs. value | Grocery & Food lead in volume; Shopping, Utilities & Education lead in total value; Education has the highest average transaction amount |
| Age group vs. merchant spending | 26–35 spends most on Shopping & Grocery; 36–45 spreads across Utilities, Shopping & Education |
| Age group fraud susceptibility | 18–25 and 56+ are most prone to fraud |
| State network infrastructure | Maharashtra has the best infrastructure; 5G growth is visible; 4G remains dominant |
| Bank transaction volume | SBI handles ~25% of all transactions, followed by HDFC |
| Bank failure rates | SBI has the most absolute failures; Yes Bank has the highest failure percentage |
| Bank fraud rates | Fraud % is fairly uniform across banks (0.16%–0.25%) |
| Network type vs. failures | 3G: 5.22% failure rate vs. 5G: 4.86% — slower networks correlate with higher failures |
| Peak transaction hours | Transactions peak around 12 PM and 7 PM |
| Hourly failure & fraud rates | Failures and frauds are both elevated between 12 AM – 6 AM |
| Device vs. average spend | All device types show similar average expenditure (~₹1,300+) |
| Amount vs. fraud | Transactions in the ₹15,000–₹20,000 range are disproportionately flagged as fraud |
| Day of week vs. age group spend | Younger users (26–35) consistently spend more throughout the week; older groups spend less overall |

---

## 🛠️ Tech Stack

| Tool | Use |
|------|-----|
| Python 3.x | Core language |
| Pandas | Data manipulation, groupby, pivot tables |
| NumPy | Numerical operations |
| Matplotlib | Bar charts, line plots, histograms, pie charts |
| Seaborn | Countplots, boxplots, heatmaps |
| Jupyter Notebook | Interactive analysis environment |

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Simple-Aditya/EDA-UPI-Transactions.git
   cd EDA-UPI-Transactions
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Download the dataset** from Kaggle and place it at:
   ```
   /kaggle/input/upi-transactions-2024-dataset/upi_transactions_2024.csv
   ```
   Or update the file path in the notebook's first cell to match your local setup.

4. **Launch the notebook**
   ```bash
   jupyter notebook eda-upi-transactions.ipynb
   ```

---

## 💡 Key Takeaways

- UPI is predominantly used for **small, everyday transactions** — grocery, food, and P2P transfers — with 75% of payments under ₹1,600.
- The **26–35 age group** drives the majority of UPI activity on both the sender and receiver side.
- **Fraud is rare (0.19%)** but disproportionately targets younger (18–25) and older (56+) users, and is concentrated in **late-night hours (12 AM – 6 AM)** and **high-value transactions (₹15K–₹20K)**.
- **SBI dominates volume** (~25% of all transactions) but Yes Bank has the highest failure rate — volume alone doesn't reflect reliability.
- **Network quality matters** — 3G connections see measurably higher failure rates (5.22%) than 5G (4.86%).
- Despite device differences, **spending behaviour is uniform** across Android, iOS, and Web users.

---

## 👤 Author

**Aditya**  
B.Com (Hons.) | Hansraj College, University of Delhi  
Data Analyst | Python · SQL · Power BI

🔗 [GitHub](https://github.com/Simple-Aditya)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
