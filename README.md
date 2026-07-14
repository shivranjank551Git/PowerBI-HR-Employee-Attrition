# HR Employee Attrition Dashboard (Interactive Power BI Visualization)

## 📌 Project Overview
This repository contains an interactive **HR Employee Attrition Dashboard** built using **Power BI Desktop**. This project was completed as part of **Task 03** for my data analytics internship with **SkillCraft Technology**. 

The main objective of this dashboard is to answer the critical business question: **"Why are employees leaving?"** and identify the key factors driving workforce turnover. It allows HR managers to drill down and filter the analytics by **Department**, **Age Group**, and **Business Travel** to make data-driven retention decisions.

---

## 📊 Key Insights & Core Questions Answered
*   **Who is leaving?** High-turnover roles are identified using a breakdown of attrition across specific Job Roles.
*   **Does workload drive attrition?** We analyze the direct impact of **Overtime** on employee burnout and departure rates.
*   **Does compensation play a role?** A custom scatter plot cross-references **Monthly Income vs. Salary Hikes** to check if top performers are leaving due to under-compensation.
*   **Are career paths stagnant?** We track the correlation between the **Years Since Last Promotion** and the rate at which employees exit.
*   **Does management matter?** The dashboard highlights attrition trends based on employee tenure with their current manager.

---

## 🛠️ Data Processing & Custom Features
To prepare the dataset for visualization, the following data engineering and modeling steps were performed:

### 1. Power Query & Data Transformation
*   **Age Group Buckets:** Since raw age is a continuous variable, I created a conditional column in Power Query to group employees into logical age brackets:
    *   `18-25`
    *   `26-35`
    *   `36-50`
    *   `50+`

### 2. DAX Calculations (Key Metrics)
I developed custom DAX measures to calculate the key performance indicators (KPIs) dynamically:

*   **Total Employees:**
    ```dax
    Total Employees = COUNT('HR_Attrition'[EmployeeNumber])
    ```
*   **Attrition Count:**
    ```dax
    Attrition Count = CALCULATE(COUNT('HR_Attrition'[EmployeeNumber]), 'HR_Attrition'[Attrition] = "Yes")
    ```
*   **Attrition Rate (%):**
    ```dax
    Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)
    ```

---

## 🖥️ Dashboard Features & Visuals
*   **KPI Summary Cards:** Quick-glance metrics representing Total Headcount, Attrition Count, and overall Attrition Rate.
*   **Interactive Slicers:** Dynamic sidebar/top-bar filters allowing instant drill-downs by **Department** and **Age Group**.
*   **Scatter Plot Analysis:** Explores the intersection of employee income, performance, and salary hikes, utilizing details-level granularity and custom tooltips for rich metadata.
*   **Interactive Tooltips:** Custom-built hover menus displaying detailed employee details (e.g., Performance Rating, Department, Job Role) on visual markers.

---

## 📂 Repository Contents
*   `HR_Attrition_Dashboard.pbix` — The main Power BI dashboard file.
*   `WA_Fn-UseC_-HR-Employee-Attrition.csv` — The raw HR dataset used for the project.
*   `README.md` — Project documentation.



