# Data Jobs Salary Dashboard #

## Project Background ##
In January 2025, the World Economic Forum released the Future of Jobs Report 2025, showing transformations in demanded skills and the job market in 2025. Based on the report, some jobs in Technology, Data, and Renewable Energy are projected to be growing fast. These are 15 fastest growing jobs in 2025-2030, and 3 of them are data related jobs.

![Fastest Growing Jobs 2025-2030](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/WEF%20Report.jpg)
*Fastest Growing Jobs 2025-2030, World Economic Forum: Future of Jobs Report 2025*

This finding, drives me to do a further research about data jobs, especially data analyst which still related to my experience, to gain more information related to data jobs salary and count of job posted, based on country where the jobs were opened, type of the job, and platforms where it was posted. I created a dashboard to show how is the trend in data jobs and gain insights for my consideration in my future career. This research used real data job information in 2023. 

## Summary ##
![Salary Dashboard](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/Salary%20Dashboard%20Project.gif)
                                                *Salary Dashboard*

With dashboard above, I can visually show some key informations extracted from data job postings 2023, such as median salary for each data jobs differentiate on type of the jobs and country where the jobs are opened, also top platform where the jobs were posted and count of the jobs posted. For the first insight, median salary of data analyst jobs ranging from USD 44,000 to USD 400,000. The lowest median salary is in Algeria with USD 44,100, but with only 2 jobs count, full-time job only, and the top job platform is Ai-Jobs.net. The highest median salary is in Belarus with USD 400,000, but with only 1 job count, full-time job only, and the top job platform is GeekLink. In Indonesia, median salary for full-time data analyst is USD 76,043 , with 14 jobs count, and the top job platform Ai-Jobs.net. This number is quite high compared to average minimum salary in Indonesia that only USD 2,400 (annualy), with the lowest is USD 1,570 and the highest is USD 3,906. In the United States, as the leading country in tech industry, the median salary for full-time data analyst is USD 90,000, with 6,480 jobs count, and the top job platform is Indeed. 

## Key Insights ##

- Algeria has the lowest full-time data analyst median salary with USD 44,100 and with only 2 jobs count 

![Algeria Median Salary](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/Algeria.jpg)
                                                *Data Analyst Median Salary in Algeria*

- Belarus has the highest full-time data analyst median salary with USD 400,000 but with only 1 job count

![Belarus Median Salary](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/Belarus.jpg)
                                                *Data Analyst Median Salary in Belarus*

- Median salary for full-time data analyst in Indonesia is USD 76,043 with 14 jobs count, 31 times higher than its average minimum salary (USD 2400 annualy)

![Indonesia Median Salary](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/Indonesia.jpg)
                                                *Data Analyst Median Salary in Indonesia*

- Median salary for full-time data analyst in the US is USD 90,000 with 6,480 jobs count and multiple choices of job type (full-time, part-time, contractor, internship, temp work)

![United States Median Salary](https://github.com/Dwisetiyawan/Salary-Dashboard-Project/blob/main/Documentation/United%20States.jpg)
                                                *Data Analyst Median Salary in United States*

## Recommendations ##

Based on the findings from the data jobs in 2023, supported by future of jobs report 2025 from World Ecnomic Forum, data analyst is one of the career path choice that offer quite high salary. The median salary of full-time data analyst In Indonesia (as I live in Indonesia) is 31 times higher than average minimum salary of Indonesia. Thus, the next step I need to take is analyze what skills do I need to be a data analyst in Indonesia and how it correlate with the salary. The analysis would be shared on my next project Salary and Skills Analysis Project. 

## Caveats ## 

- This analysis used 32K job postings data in 2023 that I got from free Excel course on **Luke Barrouse** youtube channel
- The raw data contain information about job title, job location, job schedule type, average yearly & hourly salary, job country,        company, job posted date, job posted platform, and skills related. 
- The raw data had already cleaned up, so I did not do data cleaning

## Skills Used ## 
- Charts (Bar & Map chart) for visual comparison of median salary classified by its job title, job schedule type and job country globally.
- Formulas & Functions :
    
    1. Utilize median function with nested if to calculate median salary based on job title, country, and job schedule type
        ```
        =MEDIAN(IF(
        (jobs[job_title_short]=A2)*
        (jobs[job_country]=country)*
        (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
        (jobs[salary_year_avg]<>0),
        jobs[salary_year_avg]))
        ```

    2. Utilize count function with nested if to count job posted based on job title 
        ``` 
        =COUNT(
        IF(
        (jobs[job_country]=country)*
        (jobs[job_title_short]=A8)*
        (ISNUMBER(SEARCH(type;jobs[job_schedule_type])));
        jobs[salary_year_avg]))
        ```
- Data Validation to make filtered list, filtering the result showed based on job title, country, and job schedule type chosen 
