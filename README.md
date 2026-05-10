# Hypertension-Patient-Care-Treatment-Analysis
Healthcare / Hospital Analytics

## Project Overview
This project focuses on analysing hypertension patient care data from a hospital’s Cardiology Department using Microsoft Power BI. 
The healthcare industry relies heavily on data-driven decision-making to improve patient outcomes, optimize treatment strategies, and manage healthcare costs effectively.

The analysis was conducted to help hospital management understand patient visit patterns, treatment performance, follow-up requirements, and variations across demographic and geographic groups.

## Problem Statement 
The hospital management team needed insights into:
- Patient visit trends
- Treatment costs
- Treatment success rates
- Follow-up requirements
- Performance differences across age groups and locations
  
The analysis helps healthcare stakeholders make informed operational and clinical decisions.

## Data Sourcing 
The dataset used for this project was a simulated healthcare dataset containing hypertension patient visit records.
### Dataset Details
- Source: Simulated Healthcare Dataset
- Industry: Healthcare
- Department: Cardiology
- Disease Focus: Hypertension
- Time Period: 12 Months
- Total Records: 3,000 Patient Visit Records
### Data Dictionary
| Column name              | Description                                           | Data Type  |
|--------------------------|-------------------------------------------------------|------------|
| patient_id               |                                                       |            |
| doctor ID                |                                                       |            |
| patient_visit_id         |                                                       |            |
| patient_visit Date       |                                                       |            |
| treatment_cost           |                                                       |            |
| severity_level           |                                                       |            |
| treatment_type           |                                                       |            |
| treatment_success        |                                                       |            |
| follow-up_required       |                                                       |            |
| location                 |                                                       |            |
| patient_age              |                                                       |            |
| gender                   |                                                       |            | 

## Data Transformation & Cleaning 
The raw dataset was loaded, cleaned and transformed in Power Query before analysis.
### Data Cleaning Steps
- Removed duplicate records
- Standardized text values
- Corrected data types
- Removed unnecessary columns
- Created surrogate keys using Index Columns
- Handled null and inconsistent values
- Created Age Group classifications
- Built a Date Dimension table for time analysis

## Data Modelling (Power BI) 
A Star Schema data model was implemented in Power BI to optimize reporting performance and maintain proper relational structure.
##### Fact Table
- Facts_Visits
##### Dimension Tables
- Dim_Patients
- Dim_Doctors
- Dim_Location
- Dim_Treatment
- Dim_Date
##### Relationships
Relationships were created using:
- Patient ID
- Doctor ID
- Location ID
- Treatment ID
- Visit Date

All relationships were configured as:
- One-to-Many
- Single Direction Filter

## Analysis & Measures 
#### Key DAX Measures
##### 1. Total Visits
``` Total Visits = COUNT(Facts_Visits[patient_visit_id]) ```
##### 2. Total Patients
``` Total Patients = DISTINCTCOUNT(Facts_Visits[patient_id]) ```
##### 3. Completed Visits
``` Completed Visits = CALCULATE(COUNT(Facts_Visits[patient_visit_id]),Facts_Visits[patient_visit_status] = "Completed") ```
##### 4. Average Treatment Cost
``` Average Treatment Cost = AVERAGE(Facts_Visits[patient_treatment_cost]) ```
##### 5. Treatment Success Rate
``` Treatment Success Rate = DIVIDE(CALCULATE(COUNTROWS(Facts_Visits),Facts_Visits[patient_treatment_success] = "Yes"), COUNTROWS(Facts_Visits)) ```
##### 6. Follow-Up Required Rate
``` Follow-Up Required Rate = DIVIDE(CALCULATE(COUNTROWS(Facts_Visits),Facts_Visits[patient_follow_up_required] = "Yes"), COUNTROWS(Facts_Visits)) ```

## Dashboard & Visuals 
Place screenshots of your dashboard here 
#### Dashboard Features
The dashboard provides:
- KPI Monitoring
- Monthly Patient Visit Trends
- Treatment Cost Analysis
- Treatment Success Analysis by Age Group
- Follow-Up Analysis
- Location-Based Performance Analysis
- Treatment Type Distribution

## Insights & Findings 
- Patient visits peaked in August, indicating periods of increased healthcare demand.
- Mild hypertension cases generated the highest average treatment cost.
- Young Adults (19–35) recorded the lowest treatment success rates among all age groups.
- Moderate severity cases showed the highest follow-up requirement rates.
- Treatment outcomes varied across locations, with Abuja performing highest and Ibadan lowest.
- Lifestyle Therapy, Medication, and Monitoring were all heavily utilized in hypertension management.

## Recommendations 
- Increase healthcare staffing during high-visit periods.
- Strengthen hypertension intervention programs for young adults.
- Investigate factors contributing to lower treatment outcomes in some locations.
- Improve follow-up systems for moderate severity patients.
- Expand preventive healthcare education and lifestyle management programs.

## Conclusion 
This project successfully delivered a healthcare analytics dashboard that provides actionable insights into hypertension patient care and treatment performance using Microsoft Power BI.
The dashboard enables hospital stakeholders to monitor operational performance, evaluate treatment effectiveness, and support better healthcare planning decisions.



## Skills Demonstrated
- Data Cleaning
- Data Modeling
- DAX Calculations
- Dashboard Design
- Healthcare Analytics
- Data Visualization

























