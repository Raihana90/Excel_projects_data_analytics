
# Project 2 Analysis

## Introduction

As a job seeker, I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land a higher pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_salary

       <img width="307" height="422" alt="powerquery1" src="https://github.com/user-attachments/assets/8d51e1a6-2fec-42f0-b079-3f1d47329660" />

    - 🛠️ data_job_skills  

       <img width="306" height="465" alt="powerquery2" src="https://github.com/user-attachments/assets/f09b189f-d099-412b-8c64-4503545c3723" />  


#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_salary   
      



    <img width="1913" height="988" alt="powerquery3" src="https://github.com/user-attachments/assets/d39e4016-5f95-4776-8b72-96b5528bf59c" />
  


    - 🛠️ data_job_skills
 

      

  <img width="1918" height="987" alt="powerquery4" src="https://github.com/user-attachments/assets/6adb97da-32bf-4916-9e56-61727ff654c5" />

  


### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Senior Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

  <img width="812" height="501" alt="skills better pay" src="https://github.com/user-attachments/assets/7c3c7f89-fabd-4a7e-8c79-6403027b8950" />  


#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added a new measure to calculate the median salary for United States jobs using DAX.
    ```
    =CALCULATE(
      ([Median Salary],
        data_jobs_salary[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary, I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_salary[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Senior Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.
- 
  <img width="960" height="391" alt="nonusa" src="https://github.com/user-attachments/assets/54921f92-4f72-4636-9231-899e4f8d33fe" />
  
  
#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_salary` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.


<img width="831" height="692" alt="model" src="https://github.com/user-attachments/assets/a1dcfd75-9991-43fc-93d2-8403aec228bc" />



#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and make it easy to create measures.

  
    <img width="1908" height="816" alt="pivot" src="https://github.com/user-attachments/assets/0c59f5e8-b9c2-46c4-9398-ce0cbd492cd8" />


### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS, Azure, and Tableau also show a significant presence, underlining the industry's shift towards cloud services, big data technologies, and Data visualization.  
  
<img width="650" height="391" alt="top skills" src="https://github.com/user-attachments/assets/41f980cb-4d0e-4a17-ad17-74e6cedcb53d" />  


#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, SQL, and AWS, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like Excel and SAS have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

<img width="693" height="465" alt="pay 10 skills" src="https://github.com/user-attachments/assets/6621dd83-673c-4f80-9510-929081afbaa3" />  


  
### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python, SQL, and AWS, which are evidently tied to higher-paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As a data enthusiast and a job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
