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

-- Example 1 : Show records of 'male' patients from 'southwest' region
SELECT * FROM insurance
WHERE gender = 'MALE' AND region = 'southwest';
# Insurance-Data-

-- 1. Show records of 'male' patient from 'southwest' region.

	SELECT * FROM insurance
	WHERE gender = 'MALE' AND region = 'southwest';

-- 2. Show all records having bmi in range 30 to 45 both inclusive.

	SELECT *
	FROM insurance
	WHERE bmi >=30 and bmi <= 45;

-- 3. Show minimum and maximum bloodpressure of diabetic patient who smokes. Make column names as MinBP and MaxBP respectively
	SELECT min(bloodpressure) AS MinBp, max(bloodpressure) AS MaxBP
	FROM insurance
	WHERE smoker = 'yes'AND diabetic = 'yes';

-- 4. Find no of unique patients who are not from southwest region.
	SELECT DISTINCT PatientId
	FROM insurance
	WHERE region NOT IN ('southwest');

-- OR 
	SELECT DISTINCT PatientId
	FROM insurance
	WHERE NOT region ='southwest';

-- 5. Total claim amount from male smoker.
	SELECT sum(claim)
	FROM insurance
	WHERE gender = 'male'AND smoker = 'yes';

-- 6. Select all records of south region.

	SELECT * from insurance
	WHERE region = 'southwest';

-- 7. No of patient having normal blood pressure. Normal range[90-120]

	SELECT count(PatientID)
	FROM insurance
	WHERE bloodpressure BETWEEN 90 AND 120;

/* 8.  No of pateint belo 17 years of age having normal blood pressure as per below formula -
-  BP normal range = 80+(age in years × 2) to 100 + (age in years × 2)
- Note: Formula taken just for practice, don't take in real sense. */

	SELECT COUNT(PatientID)
	FROM insurance
	WHERE age < 17 AND bloodpressure BETWEEN (80 + age * 2) AND (100 + age * 2);

-- 9. What is the average claim amount for non-smoking female patients who are diabetic?

	SELECT AVG(claim)
	FROM insurance
	WHERE smoker = 'no' AND gender = 'female' AND diabetic = 'yes';

-- 10. Write a SQL query to update the claim amount for the patient with PatientID = 1234 to 5000.

	UPDATE insurance
	SET claim = 5000
	WHERE PatientID = 1234;

-- 11.  Write a SQL query to delete all records for patients who are smokers and have no children.

	DELETE  FROM  insurance
	WHERE smoker = 'yes' AND children = 0;



