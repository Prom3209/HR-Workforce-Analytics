# HR Workforce Analytics Dashboard 📊

An end-to-end HR analytics project built using PostgreSQL, SQL, Excel, and Power BI to analyze employee attrition, workforce demographics, compensation trends, and overtime patterns.

This project demonstrates how raw HR data can be transformed into actionable business insights through database management, SQL analytics, and interactive dashboard reporting.

---

## Dashboard Preview

<img width="1161" height="661" alt="HR Dashboard" src="https://github.com/user-attachments/assets/aefbb7c2-f5d4-41a4-81f3-94ea804e68dc" />

<img width="1752" height="1013" alt="Dashboard Overview" src="https://github.com/user-attachments/assets/79a376d4-fd6b-461d-8bfd-d7535e382a71" />

<img width="1663" height="918" alt="Workforce Analysis" src="https://github.com/user-attachments/assets/88589b86-6a30-4dfa-9154-51cc16438785" />

<img width="1833" height="861" alt="Attrition Insights" src="https://github.com/user-attachments/assets/f3089dd2-b7d0-4014-a751-d656765fb47b" />

<img width="1862" height="915" alt="Compensation Analysis" src="https://github.com/user-attachments/assets/37726e53-1b47-4eaf-918e-0b3401303291" />

---

## Project Overview

This project focuses on analyzing:

- Employee attrition
- Workforce demographics
- Compensation trends
- Overtime patterns
- Departmental turnover

The objective was to simulate a real-world HR analytics workflow by transforming raw HR datasets into structured insights that support strategic business decision-making.

---

## Project Architecture

Kaggle Dataset → Excel Cleaning → PostgreSQL Database → SQL Analysis → Power BI Dashboard

---

## Project Workflow

1. Collected the HR Analytics dataset from Kaggle
2. Cleaned and prepared the dataset using Microsoft Excel
3. Imported the cleaned dataset into PostgreSQL
4. Performed SQL analysis and data exploration
5. Connected PostgreSQL to Power BI
6. Built an interactive HR Analytics dashboard

---

## Tools & Technologies

- PostgreSQL
- SQL
- Power BI
- Microsoft Excel
- pgAdmin 4

---

## Database Integration

The project uses PostgreSQL as the backend relational database for storing and analyzing workforce data before visualization in Power BI.

---

## Database Design

The project uses a PostgreSQL table called `employees` to store structured HR workforce data for reporting and analysis.

### Employees Table Structure

```sql
CREATE TABLE employees (
    age INT,
    attrition VARCHAR(10),
    business_travel VARCHAR(50),
    daily_rate INT,
    department VARCHAR(100),
    distance_from_home INT,
    education INT,
    education_field VARCHAR(100),
    employee_count INT,
    employee_number INT PRIMARY KEY,
    environment_satisfaction INT,
    gender VARCHAR(20),
    hourly_rate INT,
    job_involvement INT,
    job_level INT,
    job_role VARCHAR(100),
    job_satisfaction INT,
    marital_status VARCHAR(50),
    monthly_income INT,
    monthly_rate INT,
    num_companies_worked INT,
    over18 VARCHAR(5),
    overtime VARCHAR(10),
    percent_salary_hike INT,
    performance_rating INT,
    relationship_satisfaction INT,
    standard_hours INT,
    stock_option_level INT,
    total_working_years INT,
    training_times_last_year INT,
    work_life_balance INT,
    years_at_company INT,
    years_in_current_role INT,
    years_since_last_promotion INT,
    years_with_curr_manager INT
);
```

---

## SQL Analysis & Insights

### Total Number of Employees

```sql
SELECT COUNT(*) AS total_employees
FROM employees;
```

### Employee Attrition Analysis

```sql
SELECT 
    attrition,
    COUNT(*) AS employee_count
FROM employees
GROUP BY attrition;
```

### Department Turnover Analysis

```sql
SELECT 
    department,
    COUNT(*) AS attrition_count
FROM employees
WHERE attrition = 'Yes'
GROUP BY department
ORDER BY attrition_count DESC;
```

### Overtime vs Attrition

```sql
SELECT 
    overtime,
    attrition,
    COUNT(*) AS total
FROM employees
GROUP BY overtime, attrition;
```

### Average Salary by Job Role

```sql
SELECT 
    job_role,
    AVG(monthly_income) AS average_salary
FROM employees
GROUP BY job_role
ORDER BY average_salary DESC;
```

### Job Satisfaction Analysis

```sql
SELECT 
    job_satisfaction,
    COUNT(*) AS employee_count
FROM employees
GROUP BY job_satisfaction
ORDER BY job_satisfaction;
```

### Workforce Gender Distribution

```sql
SELECT 
    gender,
    COUNT(*) AS total_employees
FROM employees
GROUP BY gender;
```

### Educational Background Analysis

```sql
SELECT 
    education_field,
    COUNT(*) AS total
FROM employees
GROUP BY education_field
ORDER BY total DESC;
```

---

## Key Dashboard Features

- Employee Attrition Analysis
- Overtime vs Attrition Insights
- Salary Analysis by Job Role
- Workforce Demographics
- Interactive Slicers & Filters
- KPI Tracking
- Department Turnover Analysis

---

## Key Business Insights

- Employees working overtime experienced higher attrition rates
- Certain departments showed significantly higher turnover
- Salary trends varied across job roles and departments
- Workforce demographic analysis supported HR decision-making
- Job satisfaction levels influenced employee retention patterns

---

## Skills Demonstrated

- Data Cleaning & Preparation
- SQL Querying
- PostgreSQL Database Management
- Data Analysis
- Data Visualization
- Power BI Dashboard Development
- Business Intelligence
- HR Analytics
- Data Storytelling

---

## About Me

I am an HR & Payroll professional transitioning into Data Engineering and Data Science, combining operational business experience with technical analytics skills. This project demonstrates my ability to transform raw workforce data into actionable insights using SQL, PostgreSQL, and Power BI.
