# 📊 Power BI Report – Customer Churn Analysis for Databel

## 📁 Project Overview

This Power BI report analyzes customer churn for a fictional telecom provider called **Databel**. As a consultant, the goal was to explore the key drivers behind churn and provide actionable insights to reduce customer attrition.

The dataset includes customer-level information: demographics, contract types, data plans, charges, international usage, and customer service interactions.

---

## 🎯 Problem Statement

Databel has an overall churn rate of **26.86%**, which is considered high. This report investigates:
- Which customer segments are more likely to churn
- What reasons contribute to churn
- What strategies can help retain customers

---

## 🧭 Report Structure

### 🔹 Page 1: Overview

Summary of churn and key influencing factors:
- Total customers
- Total churned customers
- Churn rate
- Churn reasons and categories
- Average monthly charge
- Churn rate by:
  - Group plan size
  - U.S. state
  - Account length and contract type

### 🔹 Page 2: Customer Profiles

Analysis of churn across customer segments:
- Customers and churn rate by age
- Churn rate by demographic group (Senior, Under 30, Other)
- Churn rate by group size
- Churn rate by gender

### 🔹 Page 3: Behavior & Billing

Customer behavior, billing, and service-related churn factors:
- Avg. international charges
- Avg. extra data charges
- Customer service calls and average per customer
- Churn rate by:
  - Monthly vs yearly contracts
  - Grouped data consumption
  - Unlimited data plan
- Avg. support calls by state and churn label
- Customers and churn rate by payment method

---

## 🧮 Calculated Columns

<pre>```DAX
Churned = IF('Databel - Data'[Churn Label] = "Yes", 1, 0)

Demographics = IF('Databel - Data'[Under 30] = "Yes", "Under 30", 
                  IF('Databel - Data'[Senior] = "Yes", "Senior", "Other"))

Contract Category = SWITCH('Databel - Data'[Contract Type],
                           "One Year", "Yearly",
                           "Two Year", "Yearly",
                           "Monthly", "Monthly")

Grouped Consumption = IF('Databel - Data'[Avg Monthly GB Download] < 5, "Less than 5 GB",
                         IF('Databel - Data'[Avg Monthly GB Download] < 10, "Between 5 and 10 GB", 
                         "10 or more GB")) </pre>

## 📏 Measures
<pre>```DAX

Number of churned customers = SUM('Databel - Data'[Churned])

Churn Rate = DIVIDE([Number of churned customers], [Number of customers])

Number of customers = COUNTROWS('Databel - Data')

Average Customer Support Calls = AVERAGE('Databel - Data'[Customer Support Calls]) </pre>

## 🔍 Key Insights

The top three reasons why customers churned are:

-Competitor made better offer
-Competitor had better devices
-Attitude of support person

Customers on monthly contracts churn significantly more than yearly contract holders.
The customers that doesn't belong to a group are more likley to churn. 

The group that has the lowest churn rate is group 6

Seniors have a churn rate about 10% above average.

California has an exceptionally high churn rate (~63%) with fewer support calls — an anomaly worth investigating.

Customers with unlimited data plans and those who frequently contact support are more likely to churn.

## ✅ Recommendations

Incentivize long-term contracts to reduce churn.

Target high-risk segments: seniors, heavy data users without unlimited plans, and customers who frequently contact support.

Review customer satisfaction in low-support but high-churn states (e.g., California).

Monitor and optimize international plan offerings to match customer behavior and avoid dissatisfaction.

## 📌 Notes

This project was created for exploratory and demonstration purposes using a fictional dataset. All data and insights are hypothetical.


