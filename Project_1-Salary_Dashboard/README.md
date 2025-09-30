# Excel Salary Dashboard  

![vid1 gif(1)](https://github.com/user-attachments/assets/510042fa-1fc2-402d-ad6f-7ff8740ae01b)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. The data provides a foundation for analyzing data using Excel. The data contains detailed information on job titles, salaries, locations, etc...

### Dashboard File
My final dashboard is in [My_project_salary_dashboard.xlsx](My_project_salary_dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart  

<img width="555" height="283" alt="job title" src="https://github.com/user-attachments/assets/1654e16e-c1ad-439d-a239-3c4c19dba7bd" />

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

![gif2](https://github.com/user-attachments/assets/271aaba7-80c4-4e88-82d9-f570d13907cb)

- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[salary_year_avg]<>0)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
    jobs[salary_year_avg]
  )
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table     

<img width="382" height="272" alt="table1" src="https://github.com/user-attachments/assets/69d1efc5-71d7-4f88-8ee4-ff5bbfb3d37a" />   

📉 Dashboard Implementation      

<img width="563" height="572" alt="job title dashboard" src="https://github.com/user-attachments/assets/23dfa415-c6af-489c-84fd-ef3f76871625" />

#### ⏰ Count of Job Schedule Type

```
=FILTER(M2#,NOT(ISNUMBER(SEARCH("and",M2#)))*(M2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table  

<img width="158" height="167" alt="sorted type" src="https://github.com/user-attachments/assets/27e61092-ba5b-4a10-9b82-417c220e7f23" />  

📉 Dashboard Implementation:    
 
<img width="562" height="570" alt="type" src="https://github.com/user-attachments/assets/6e6050b4-e45f-45f5-aa50-4fb3b8eb23b7" />


### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced  


![Pause GIF image](https://github.com/user-attachments/assets/4c3aba46-fcf4-43e2-87d7-1524bbe7051f)





## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing a real data, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
