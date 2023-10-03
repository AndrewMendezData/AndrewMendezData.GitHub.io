# A Dive into Hospital Data

<img src="images/qSQLprojectpic.png?raw=true">

This project was the third in the Data Analytics Bootcamp led by Avery Smith. This project helped me explore more Advanced SQL and see which tools are at our disposal as analysts to extract meaning from data.<br>

---

Hospitals are one the most important "arteries of society", if you will. They help keep communities healthy and live longer lives. It's important, though, to do a self-check to ensure that hospitals are running efficiently and are producing the result that they are meant to produce. An big-picture analysis could help give us some insight into what needs to improve to continue provide quality care in hospitals around the country.<br>

### Objectives
*I am assisting some hospital administrators in answers the following questions:*
<ol>
  1. What is the distribution of time spent in the hospital?<br>
  2. Is there a relationship between the number of procedures a patient has and how long they stay in the hospital?<br>
  3. What medical specialties are doing the most number of procedures on average?<br>
  4. Is the hospital treating patients of different races differently, specifically with the number of lab procedures done?<br>
  5. The Hospital Administrators wanted to highlight some of the biggest success stories of the hospital. They are looking for instances where patients came into the hospital with an emergency (admission_type_id of 1) but stayed less than the average time in the hospital.<br>
  6. A written summary for the top 50 patients in procedures and total medications.
</ol>

### The Data
The data is from a Kaggle dataset containing information on 130 US Hospitals from the years 1999-2008.<br>
You can find the data [here](https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/data?select=diabetic_data.csv).

### Key Insights
*From this analysis, we found:*
<ol>
  1. The most common stay for patients in the hospital is 3 days.<br>
  2. The time that patients stay in the hospital increases in relation to the amount of procedures that patient has received.<br>
  3. It appears that Thoracic Surgery has the highest average procedures across all the medical specialties in included in this dataset.<br>
  4. African Americans have the highest average rate of procedures overall.
</ol>

### Analysis
**What is the distribution of time spent in the hospital?**<br>
For this question, I created a histogram using SQL code to help illustrate the distribution. I used this query:<br>
<img src="images/q1 histogram result.png?raw=true"><br><br>

From this query, SQL returned:<br>
<img src"images/q1 sql code histogram.png?raw=true"><br><br>

From this SQL histogram, we can see that the most common amount of time that patients stay in the hospital is 3 days. Further analysis could be conducted to find why a 3-day timeframe is the most common.<br><br>


**Is there a relationship between the number of procedures a patient has and how long they stay in the hospital?**<br>
For this question, I found the average time, in days, the patients were in the hospital depending on the amount of procedures they had: few = 0-24, average = 25-54, many = 55+.<br>
Here was the query:<br>
<img src="images/q2 avg amoount result.png?raw=true"><br><br>

I made sure to use the ROUND statement to shorten the numbers returned and ORDER BY DESC to see the highest amount of days first.<br>

Here was the result:<br>
<img src"images/q2 avg amount query.png?raw=true"><br><br>

We see that the higher amount of procedures a patient has, the longer that patient stays in the hospital. This could inform decisions on which procedures are being overprescribed? Hospitals could dig deeper and see if less invasive methods could be practiced to help further reduce the time that patients spend in hospitals.<br><br>


**What medical specialties are doing the most number of procedures on average?**<br>
My query to explore this question:<br>
<img src="images/q3 med spec query.png?raw=true"><br><br>

SQL returned:<br>
<img src"images/q3 med spec result.png?raw=true"><br><br>

With this data, we can see that the Thoracic Surgery specialty is the one being utilized the most in terms of average procedures. This could help inform decisions about funding allocation and residency program organization to focus more energy in this specialty to improve patient outcomes.<br><br>


**Is the hospital treating patients of different races differently, specifically with the number of lab procedures done?**<br>
For this query, I used the JOIN statement to bring together two tables in the "patient" database; "health" & "demographics". Here is the query I used:<br>
<img src="images/q4 query.png?raw=true"><br><br>

Here is the return:<br>
<img src"images/q4 result.png?raw=true"><br><br>

From the resulting data, it appears that African Americans have the highest average number of lab procedures (though not too far off from the others, still the highest). More analysis could uncover why this could be. We also found that there is a high number of patients in the database without a race value. This could shed light on an administrative issue during intake that should be addressed to keep accurate and complete data on file.<br><br>


**The Hospital Administrators wanted to highlight some of the biggest success stories of the hospital. They are looking for instances where patients came into the hospital with an emergency (admission_type_id of 1) but stayed less than the average time in the hospital.**<br>
To find this specific data, I used the following query:<br>
<img src="images/q5 query.png?raw=true"><br><br>

I used a CTE (common table expression), avg_time, to clarify the statement in the query. This resulted in the patients who admitted as an emergency but were well enough to be discharged quicker than the average stay in the hospital.<br><br>


**A written summary for the top 50 patients in procedures and total medications.**<br>
For this query, I had to use the CONCAT statement to put together full sentences that included that data that the administration was requesting. The query includes the CASE WHEN statement to alternate between whether the patient was readmitted to the hospital or not. There is also an INNER JOIN included because the demographic information was on a separate table from the data on medications & procedures. Here was the query:<br>
<img src="images/q6 query.png?raw=true"><br><br>

Here is the resulting information:<br>
<img src"images/q6 result.png?raw=true"><br><br>

This information is useful to combine multiple pieces of information to create a cohesive statement that is easy to digest. It can help clarify a general relation between certain pieces of data.<br><br>


### Conclusions
It's clear that the more procedures a patient has, the longer they tend to stay in the hospital. Most patients spend 3 days in the hospital, average as 4.4 days; this information can help inform further analysis into how to reduce 3 days to 2 days and help save money for the hospital to use elsewhere. The data also showed that African American patients have the highest average rate of lab procedures. Further research could uncover the cause of this and if there is a presence of bias in hospital protocol.

### Personal Notes
This analysis has uncovered some interesting results that lead to more questions. These insights could lead to answers that could help hospitals become more efficient and effective, and maybe even save some money!<br><br>
Thank you for reading through the project! Please provide feedback as I'm using these practice projects to break through into the world of data. I'm open to work and new data opportunities! Connect with me!<br><br><br>

*This project is from a Data Analytics Bootcamp and is not meant to provide actionable insight. Its purpose is to showcase skill and depth of knowledge in the field of Analytics.*

