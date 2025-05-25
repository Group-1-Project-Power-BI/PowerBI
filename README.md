# HR-Dataset
This project aims to analyse and visualise the Performance of Employees' data in the Company for 2012-2022. The data is sourced from the HR_dataset and has been processed using Power BI for easy management and analysis. This project showcases our skills in Power BI as I go through data cleaning, analysing and visualising the layoffs dataset.
## Table of Contents

- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- Validation
- Modeling
- [Data Analysis](#data-analysis)
- [Visualizations](#visualizations)
- [Limitations/Assumptions](#limitationsassumptions)
  
## Data Sources
The HR dataset was sourced from Google Drive. You can find the raw file at https://drive.google.com/drive/folders/1F6OBnq8BEPWrkvGa9n0ZKLM7CIemSnVw

## Tools
- Power  Query( ETL, Conditional Columns, Custom Columns using M Language)
- Power Pivot (DAX)
- Data Modelling

##  Data Cleaning
1-**Setting the First Row as a Header**

2-**Removing Null Values**
  
3-**Removing Empty Columns**

4-**Renaming Unclear Titles**

5-**Capitalizing Each Word in Columns**

6-**Merging First and Last Name Columns into Full Name**

7-**Splitting Hire Date into Day, Month, and Year**

 8-**Replacing City Values**:
 'NY' with 'New York', 'IL' with 'Illinois', and 'CA' with 'California'.
    
9-**Conditional Columns**
- **Age Categories**: We created a conditional column to classify employees into different age categories based on their ages.
  - **Categories**: 
    - Young Adult (18-29)
    - Middle Adult (30-39)
    - Older Adult (40-51)


**Distance Categories**: We created a conditional column to group employees based on their distance from the office.
  - **Categories**: 
    - Nearby (1-15)
    - Far (16-30)
    - Very Far (31-45)
      
**Experience Categories**: We created a conditional column to categorize employees based on their years at the company.
  - **Categories**:
    - New Hires (0-2)
    - Mid-Level Employees (2-5)
    - Experienced Employees (5-10)

10-**Custom Columns using M Language**
- **Percentage of Training Opportunities Taken**: We used M Language to create a custom column that calculates the percentage of training opportunities taken by each employee.
##Data Analysis

##  Validation Process


**Overview**


This Power BI project aims to ensure data integrity in employee performance reviews by validating the dates of evaluations. Specifically, we check that:

o No reviews exist for employees before their hire date.

o No reviews exist for employees after their exit date.


**Data Processing Steps**

1️- Calculating Employee Exit Date

To determine the date employees left the company, we:

o Created a custom column in Power BI that adds the total years at the company to the hire date.

o This gives us an estimated exit date for each employee.

2️- Merging Exit Dates into Performance Data

o We merged queries to integrate the newly created exit date column into the performance review table.

3️- Validating and Cleaning Data


**To ensure valid reviews:**

o We added a conditional column that compares the review date with the employee's hire date and exit date.

o If the review occurred after the exit date, the data was deleted.

o If the review occurred before the hire date, the data was removed.

Issue Identified

· Initial review of the source data indicated 190 missing reviews.

· A validation process was conducted to ensure completeness and accuracy.


**Validation Results**

After a thorough validation process, updated analysis revealed:

· The actual number of missing reviews was found to be 390, correcting an earlier underestimation.


## Modeling

**Overview**

This Power BI project is designed to analyze employee performance, satisfaction levels, and related metrics using a well-structured data model. The model consists of five interconnected tables: *Employee, Education Level, Performance Rating, Rating Level, and Satisfied Level. Relationships are established using *primary and foreign keys, enabling comprehensive insights.

**Tables and Keys**

1. Employee Table

· Fields:

o Employee ID (Primary Key)

o Education Level (Foreign Key - linked to Education Level)

o Hire Date

o Age

o Age Group

o Attrition

o Business Travel

· Primary Key: Employee ID

· Foreign Keys:

o Education Level → Education Level Table

o Employee ID → Performance Rating Table

2. EducationLevel Table

· Fields:

o EducationLevelID (Primary Key)

o EducationLevel

· Primary Key: EducationLevelID

· Foreign Keys: None

3. PerformanceRating Table

· Fields:

o Employee ID (Foreign Key - linked to Employee)

o Calculated Date

o Environment Satisfaction

o Hire Date

o Job Satisfaction Level (Foreign Key - linked to SatisfiedLevel)

o Manager Rating (Foreign Key - linked to RatingLevel)

o Relationship Satisfaction (Foreign Key - linked to SatisfiedLevel)

o Review Date

o Self Rating (Foreign Key - linked to RatingLevel)

· Primary Key: None specified

· Foreign Keys:

o Employee ID → Employee Table

o Job SatisfactionLevel → SatisfiedLevel Table

o Manager Rating → RatingLevel Table

o Relationship Satisfaction → SatisfiedLevel Table

o Self Rating → RatingLevel Table

4. RatingLevel Table

· Fields:

o RatingID (Primary Key)

o RatingLevel

· Primary Key: RatingID

· Foreign Keys: None

5. SatisfiedLevel Table

   · Fields:

o SatisfactionID (Primary Key)

o SatisfactionLevel

· Primary Key: SatisfactionID

· Foreign Keys: None

**Relationships**

· The Employee table is linked to the EducationLevel table via the Education Level field.

· The Employee table is connected to the PerformanceRating table through the Employee ID field.

· The PerformanceRating table is linked to the SatisfiedLevel table via Job SatisfactionLevel and Relationship Satisfaction.

· The PerformanceRating table is linked to the RatingLevel table via Manager Rating and Self Rating.

Usage

This model allows for data-driven analysis of employee performance, satisfaction trends, and managerial effectiveness, providing insights to enhance organizational strategies.


## Analysis process


We're analyzing a company with 1,470 employees and a 16.12% attrition rate. Let me break down the deeper insights:


1. Why do employees leave right after promotions?

Odd finding: Employees rated as "Exceeds Expectations" or "Excellent" have high attrition

Possible explanations:

o Promotions aren't accompanied by adequate salary increases

o They might perceive promotions as unfair

o Promotions could make them more visible to recruiters


2. Which branches do employees typically exit the company from )Total 237(?

o California (153) 64.56%

o (2)-New York (58) 24.47%

o (3)- Illinois (26) 10.97%


3. Why do new hires have the highest attrition (121 cases)?

Potential reasons:

o Poor onboarding process

o Reality shock - job differs from expectations

o Inadequate support during probation period


4. Why does Technology department have highest attrition (153)?

Despite lower salaries compared to other departments the average (71K vs Sales101K)

Possible reasons:

o Highly competitive tech job market

o Non-competitive compensation

o High work pressure


5. Why do medium-distance commuters (16-30km) have high attrition (81)?

o Commuting is far enough to be burdensome but not so far that they cannot find closer opportunities.


6. Why do Computer Science graduates have highest attrition (59)?

o Abundant external opportunities.

o Market pays more for same qualifications.


7. Why do high Relationship Satisfaction scores correlate with attrition?

o (Counterintuitive - 140 "Very Satisfied" left)

o Explanation: High performers can easily find better opportunities.


8. Why do mid-level employees (2-5 years) have high attrition (64)?

o Start exploring external opportunities.

o Feel stagnant in career progression.

o Promotions slow down during this period.


9. Why do Sales Representatives have high attrition (53)?

o High pressure environment

o Performance-based pay structure

o Naturally, fluid job market for sales roles


## Visualization

1. Attrition Trends

Overall Attrition Rate: 16.12%

Highest Attrition by Job Role:

o - Sales Executive (57 terminations)
o - Recruiter (136 terminations)

o - Software Engineers (445 terminations)

o - Data Scientists (409 terminations)

Highest Attrition by Department:

o - Sales (133 terminations)

o - Technology (92 terminations)

o - Human Resources (twelve terminations)

2. Employee Demographics & Satisfaction

Gender Distribution:

o - Female: 571

o - Male: 537

o - Non-Binary: 105

o - Prefer Not to Say: 20

- Age Distribution:

o - Young Adults (18-29): 760 active, 195 terminated

o - Middle Adults (30-39): 262 active, 27 terminated

o - Older Adults (40-51): 211 active, 15 terminated

- Relationship Satisfaction Impact:

o - Employees with low relationship satisfaction show higher attrition.

o - Environment Satisfaction:

o - Employees dissatisfied with their work environment show a higher turnover.


3. Factors Influencing Retention

o - Stock Options & Loyalty:

o - Employees with higher stock option levels (3 & 4) show lower attrition.

o - Business Travel & Attrition:

o - Frequent travelers experience higher attrition (208 terminations).

o - Job Satisfaction & Performance:

o - Employees dissatisfied or neutral about their job show higher attrition.

o - Employees who exceed expectations tend to stay longer.


4. Salary & Experience Insights

o - Salary Distribution:

o - Senior Software Engineers, Machine Learning Engineers, and Data Scientists earn between $320K - $510K.

o - HR-related roles, such as HR Executives and Recruiters, earn significantly less ($80K - $140K).

o - Work-Life Balance Impact:

o - Employees with higher years at the company show better satisfaction scores.
