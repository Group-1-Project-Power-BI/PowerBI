# HR-Dataset
This project aims to analyze and visualize the Performance of Employees' data in the Company for 2012-2022. The data is sourced from the HR_dataset and has been processed using Power BI for easy management and analysis. This project showcases our skills in Power BI as I go through data cleaning, analysing and visualizing the layoffs dataset.
## Table of Contents

- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Data Analysis](#data-analysis)
- [Visualizations](#visualizations)
- [Limitations/Assumptions](#limitationsassumptions)
  
## Data Sources
The HR dataset was sourced from Google Drive. You can find the raw file at https://drive.google.com/drive/folders/1F6OBnq8BEPWrkvGa9n0ZKLM7CIemSnVw

## Tools
- Power  Query( ETL, Conditional Columns, Custom Columns using M Language)
- Power Pivot (DAX)
- Data Modeling

##  Data Cleaning
**Setting the First Row as a Header**

**Removing Null Values**
  
**Removing Empty Columns**


**Renaming Unclear Titles**

**Capitalizing Each Word in Columns**

**Merging First and Last Name Columns into Full Name**

 **Splitting Hire Date into Day, Month, and Year**

 **Replacing City Values**:
 'NY' with 'New York', 'IL' with 'Illinois', and 'CA' with 'California'.
    
**Conditional Columns**
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

**Custom Columns using M Language**
- **Percentage of Training Opportunities Taken**: We used M Language to create a custom column that calculates the percentage of training opportunities taken by each employee.
