# 🛒 Freshmart Superstores Sales Performance Report

## 📊 Project Overview

This project analyzes **Freshmart Superstores’** performance across three branches — **Mandalay, Naypyitaw, and Yangon** — between **January and March 2019**.

The main goal is to uncover insights into:

* Sales and profitability across branches
* Customer demographics and buying behavior
* Product performance and payment preferences
* Daily and monthly sales trends

---
<details>
<summary>🧠 <b>Table of Contents</b></summary>

- [Project Context](#-project-context)
- [Key Questions](#-key-questions)
- [Dataset Description](#️-dataset-description)
- [Data Cleaning & Preparation](#-data-cleaning--preparation)
- [Visuals & Dashboard](#-visuals--dashboard)
- [Data Analysis & Insights](#-data-analysis--insights)
- [Key Insights Summary](#-key-insights-summary)
- [Recommendations](#-recommendations)
- [Conclusion](#-conclusion)
- [Contact](#-contact)
</details>

---

## 🎯 Objectives

The aim of this analysis is to help management make **data-driven decisions** by identifying key factors that influence sales, revenue, and customer satisfaction.

---

## 💼 Business Questions

This project answers the following key questions:

1. **Overall Performance**

   * What is the **total revenue**, **total gross income**, **total orders**, and **average rating** across all branches?

2. **Branch Comparison**

   * Which **branch or city** recorded the **highest total sales and gross income**?
   * How do these figures compare **month by month**?

3. **Customer & Gender Insights**

   * How do **sales and gross income** differ between **Member** and **Normal** customers?
   * Does **gender** influence spending or buying behavior?

4. **Product Line Analysis**

   * Which **product line** generates the **most revenue** and receives the **highest customer ratings**?

5. **Payment Preferences**

   * What are the most **preferred payment methods** among customers?
   * How do payment types relate to **total sales** and **branch locations**?

6. **Sales Trends Over Time**

   * What do the **daily and monthly sales trends** look like?
   * Which are the **peak sales hours** and **top-performing months**?

7. **Order Frequency**

   * How many **orders** are made **each day**, and are there any **peak hours**?

8. **Time-of-Day Analysis**

   * During which **time of day** does the store receive the **most orders**, and **how much revenue** is generated during those times?

     * **Morning:** 9 AM – 12 Noon
     * **Afternoon:** 12 Noon – 4 PM
     * **Evening:** 4 PM – 9 PM

---

## 🧾 Data Collection and Description

The dataset used in this project was provided by our instructor **Ms. Bolatito**. It contains detailed transaction records from **Freshmart Superstores** across three branches in **Mandalay**, **Naypyitaw**, and **Yangon**.

### **Key Data Fields**

| Field Name                      | Description                                                           |
| ------------------------------- | --------------------------------------------------------------------- |
| **Invoice ID**                  | Unique transaction code for each sale                                 |
| **Branch / City**               | Store location (A – Mandalay, B – Naypyitaw, C – Yangon)              |
| **Customer Type**               | Indicates whether the customer is a **Member** or **Normal** customer |
| **Gender**                      | Customer gender (**Male** or **Female**)                              |
| **Product Line**                | Product category (6 types — e.g., Food, Fashion, etc.)                |
| **Unit Price, Quantity, Total** | Transaction-level sales details                                       |
| **COGS, Gross Income**          | Profitability metrics for each sale                                   |
| **Payment**                     | Mode of payment (**Cash**, **Credit Card**, or **E-wallet**)          |
| **Date, Time**                  | Transaction timestamp (used for trend and time-based analysis)        |
| **Rating**                      | Customer satisfaction score (scale of **1–10**)                       |

---

## 🧰 Tools Used

* **Power BI** → Data modeling, visualization, and dashboard creation
* **Power Query** → Data cleaning and transformation
* **DAX (Data Analysis Expressions)** → Calculations and KPIs

---

## 🛠️ Data Cleaning & Transformation (Power Query)

This project uses **FreshMart Superstores Sales** data, originally provided in five tables:
`customer-details`, `product-details`, `calendar`, `city-details`, and `supermarket-sales`.

From these, I created **four dimension tables** — `dim_customer`, `dim_product`, `dim_calendar`, `dim_city` — and **one fact table**.

### 🔧 Cleaning & Preparation Steps

* **Verified Data Types:**
  Reviewed all columns across tables and ensured each had the correct data type (e.g., text, whole number, decimal, date).

* **Promoted Headers:**
  Applied header promotion to `city-details`, `customer-details`, and `product-details` tables for proper column naming.

* **Built the `dim_calendar` Table:**

  * Converted the `Date` column into a full date hierarchy: **Year → Quarter → Month → Day → Hour**.
  * Added a new **Time of Day** classification column (`Morning`, `Afternoon`, `Evening`) using conditional logic.

* **Ensured Data Quality:**

  * Removed duplicate rows from all dimension tables to maintain consistency and avoid relationship conflicts.

### ➕ Calculated Measures Created

* **Total Revenue**
* **Total Gross Income**
* **Total Orders**
* **Average Rating**

---
## 🗂️ Data Model

* **Fact Table:** Sales data (Revenue, Quantity, COGS, etc.)
* **Dimension Tables:**

  * Customers
  * Products
  * Cities
  * Date Calendar

Designed a clean star schema linking all tables:

* **Invoice ID** connects `dim_city`, `dim_customer`, and `dim_product` to the **Sales_Fact** table (**one-to-one** relationships).
* **Date** links `dim_calendar` to the **Sales_Fact** table (**one-to-many** relationship).

<br>
**Overview of data modelling**
<br>
![Sales table-Raw Data Overview](images/modeling.PNG)
<br><br>

---

## 📸 Visuals & Dashboard

**1️⃣ Overview of Dashboard**
<br><br>
![Dashboard Overview](images/dashboard.PNG)
<br><br>
**2️⃣ Revenue Report**
<br><br>
![Sales table-Raw Data Overview](images/revenue.PNG)
<br><br>
**3️⃣ Customer Segment Report**
<br><br>
![Sales table-After Cleaning Overview](images/customer_segment.PNG)
<br><br>
**4️⃣ Sales Report**
<br><br>
![Calendar table Overview](images/sales.PNG)
<br><br>
**5️⃣ Product Report**
<br><br>
![Fact table Overview](images/product.PNG)
<br><br>

---
## 📈 Key Insights

* 🏆 **Branch C (Mandalay)** recorded the **highest total sales and gross income**
* 👥 **Member customers** spent more than **Normal customers**
* 🚺 **Female customers** purchased slightly more than males
* 🍽️ **Food & Beverages** was the **top-selling product line**
* 💳 **E-wallet** and **Cash** were the most **preferred payment methods**
* ⏰ **Evening hours (4 PM – 9 PM)** had the **highest sales**
* 📅 **January** was the **top-performing month**, and **Saturdays** recorded the **highest daily sales**

---

## 💡 Recommendations

1. Management should replicate **Mandalay’s branch sales strategy** in other locations.
2. More **staff and promotions** should be added during **evening hours**.
3. Expanding the **loyalty program**, introducing a tiered reward system could
attract and retain high-value customers.
4. Increase stock and bundle offers in **Food & Beverages**.
5. Partner with **E-wallet providers** for cashback and promo deals to strengthen customer
convenience.
6. Extend **store hours** or run **weekend campaigns** to boost weekend sales.

---

## 🧾 Conclusion

This analysis highlights the key factors driving sales and profit across Freshmart branches.
By focusing on high-performing products, customer loyalty, and peak sales periods, Freshmart Superstores can **improve efficiency, boost sales, and enhance customer satisfaction**.

---

## 📬 Contact

I’d love to connect and discuss more about data analytics, visualization, or collaborative projects!

* **Author:** *Rafat Adebanjo*

💼 LinkedIn: www.linkedin.com/in/rafatadebanjo

📧 Email: aderafat.gmail.com

💻 GitHub: https://github.com/Rophah

Feel free to reach out — let’s turn data into meaningful insights together! 🚀

---


