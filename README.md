# 🩺 Insurance Database SQL Queries

This repository contains a collection of SQL queries written for exploring and analyzing an **insurance dataset** using MySQL. The project focuses on practical data analysis and query-building skills suitable for beginner to intermediate data analysts.

---

## 📁 Files Included

- `insurance.sql` – SQL script containing various queries related to patient demographics, health metrics, and insurance claim analysis.

---

## 📝 Description

This SQL file performs the following tasks:

1. **Filter patients by gender and region**
2. **Analyze BMI ranges**
3. **Summarize blood pressure for diabetic smokers**
4. **Count unique patients excluding a specific region**
5. **Calculate total claim amount for male smokers**
6. **Fetch records for specific regional data**
7. **Count patients within normal blood pressure range**
8. **Age-based dynamic blood pressure range evaluation**
9. **Average claim for non-smoking, diabetic females**
10. **Update claim amount for a specific patient**
11. **Delete smoker records with no children**

---

## 🧠 Sample Queries

```sql

-- Example: Show records of 'male' patients from 'southwest' region
SELECT * FROM insurance
WHERE gender = 'MALE' AND region = 'southwest';
# Insurance-Data-
