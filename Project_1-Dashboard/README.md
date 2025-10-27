# Excel Salary Dashboard

![1_Salary_Dashboard_Final_Dashboard.gif](/0_resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

> **"What should I really be earning?"** — Now you can find out.

---

## Introduction

I'm **Osokoya Oluwabukunmi**, a **Data Analyst in training** at **Kwara State University, Malete**.

This **interactive Excel dashboard** helps **job seekers like me** explore **real-world salary trends** in data roles — so we can **negotiate confidently** and **plan smarter careers**.

Built using a **2023 global dataset** of **32,000+ data science jobs**, this is **Project 1** of my **18-weeks Data Analyst portfolio journey**.

### Final Dashboard File
[Check out my work here !!! :  `Data_Jobs_Salary_Dashboard.xlsx`](Project_1_Osokoya-Oluwabukunmi.xlsx)

---

## Excel Skills I Mastered

| Skill | Used For |
|--------|----------|
| **📉Charts** | Bar & Map visualizations |
| **🧮Formulas & Functions** | Dynamic median salary logic |
| **❎Data Validation** | Interactive dropdown filters |

---

## Dataset Overview

Real-world **2023 data science job postings** including:

- **👨‍💼Job Titles** (Data Analyst, Engineer, Scientist, etc.)  
- **💰Salaries** (yearly & hourly)  
- **📍Locations** (190+ countries)  
- **🛠️Skills Required** (Python, SQL, AWS, etc.)

---

## Dashboard Features

### 1. Median Salaries by Job Title (Bar Chart)

![Bar Chart: Salaries by Job Title](/0_resources/Images/data_validation.png)

- **Insight:** Senior roles & Engineers earn **20–60% more** than Analysts.  
- **Design:** Horizontal bars, sorted descending for instant readability.

---

### 2. Global Salary Heatmap (Map Chart)

![Map Chart: Country Median Salaries](/0_resources/Images/maps.png)

- **Insight:** **US, Canada, Western Europe** lead in pay.  
- **Design:** Color intensity = salary level (darker = higher).

---

### 3. Dynamic Median Salary Formula

```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
  )
)

```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![1_Salary_Dashboard.png](/0_resources/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

![Salary Dashboard Title](/0_resources/Images/Salary_dashboard.png)     

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/0_resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

![Salary Dashboard Type](/0_resources/Images/schedule_type.png)

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced

![Salary Dashboard Data Validation](/0_resources/Images/data_validation_1.png)


## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from my Excel findings, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
