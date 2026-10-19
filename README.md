# 🛍️ E-Commerce Customer Churn Analysis using MySQL

## 📄 Overview
This project performs a comprehensive **customer churn analysis** for an e-commerce company using **MySQL**.  
It covers all stages from **database creation**, **data cleaning**, and **transformation** to **analytical SQL queries** that deliver valuable business insights about customer behavior, satisfaction, and churn patterns.

---

## 🗂️ Project Files
| File Name | Description |
|------------|-------------|
| **E-Commerce Customer churn db.sql** | Contains SQL commands for creating the database and inserting customer churn data. |
| **E-Commerce Customer Churn Analysis.sql** | Includes data cleaning, transformation, and analytical SQL queries for churn analysis. |

---

## ⚙️ Project Workflow

### 1️⃣ Database Creation
- Created a new database named `ecomm`.
- Defined the table **customer_churn** with key fields:
  - `CustomerID`, `Churn`, `Tenure`, `PreferredLoginDevice`, `CityTier`, `WarehouseToHome`, `PreferredPaymentMode`, `Gender`, `SatisfactionScore`, etc.
- Inserted realistic customer data including demographics, order behavior, and engagement details.

---

### 2️⃣ Data Cleaning
- **Handled Missing Values**:
  - Imputed *mean* values for:  
    `WarehouseToHome`, `HourSpendOnApp`, `OrderAmountHikeFromlastYear`, `DaySinceLastOrder`.
  - Imputed *mode* values for:  
    `Tenure`, `CouponUsed`, `OrderCount`.
- **Removed Outliers**:
  - Deleted records where `WarehouseToHome > 100`.
- **Fixed Inconsistencies**:
  - Standardized categorical values:  
    - “Phone” → “Mobile Phone”  
    - “CC” → “Credit Card”  
    - “COD” → “Cash on Delivery”

---

### 3️⃣ Data Transformation
- **Renamed Columns**:
  - `PreferedOrderCat` → `PreferredOrderCat`  
  - `HourSpendOnApp` → `HoursSpendOnApp`
- **Created New Columns**:
  - `ComplaintReceived` → “Yes” if complaint = 1, else “No”
  - `ChurnStatus` → “Churned” if churn = 1, else “Active”
- **Dropped Columns**:
  - Removed redundant columns `Churn` and `Complain`.

---

### 4️⃣ Data Exploration & Analysis
A series of **20+ SQL queries** were executed to extract insights, including:

| Query Objective | Description |
|------------------|-------------|
| 🧮 Churned vs Active Customers | Count and compare churned and active users. |
| 📈 Average Tenure & Cashback | Find average tenure and total cashback for churned users. |
| 💬 Complaint Analysis | Determine percentage of churned customers who complained. |
| 👩‍💼 Gender Distribution | Analyze complaint patterns across genders. |
| 🏙️ City Tier Insights | Identify the city tier with most churned customers. |
| 💳 Payment Behavior | Find most preferred payment mode among active users. |
| 🛒 Order Category Trends | Find top 3 product categories by average cashback. |
| 📱 Device Usage | Evaluate how app usage hours relate to churn. |

---

### 5️⃣ Additional Table: `customer_returns`
- Created a **customer_returns** table with refund details.  
- Joined it with `customer_churn` to analyze **returns from churned and complaint customers**.

---

## 📊 Key Insights
- Customers with **low satisfaction scores** and **greater warehouse distances** are more likely to churn.  
- **Mobile phone** and **credit card** users are generally more active.  
- **City Tier 1** customers show the **highest churn**, particularly in *Laptop & Accessory* category.  
- Complaints are a strong predictor of **customer churn**.

---

## 🧠 Skills & Concepts Demonstrated
- SQL Database Design  
- Data Cleaning & Imputation  
- Data Transformation  
- Aggregation & Grouping Queries  
- Conditional Logic & Subqueries  
- Table Joins & Relationships  
- Business Insights using SQL  

---

## 🚀 How to Run the Project
1. Open **MySQL Workbench** or any SQL IDE.  
2. Execute **`E-Commerce Customer churn db.sql`** to create and populate the database.  
3. Run **`E-Commerce Customer Churn Analysis.sql`** to perform data cleaning, transformation, and analysis.  
4. Explore query outputs to interpret key business insights.

---

## 🏁 Conclusion
This project showcases how SQL can be leveraged for **data-driven churn analysis** in e-commerce.  
It helps identify patterns behind customer attrition, enabling strategies to improve **retention and satisfaction**.
