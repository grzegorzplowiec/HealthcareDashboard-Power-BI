# Healthcare-Dashboard


## Problem Statement

This dashboard provides a comprehensive overview of patient wait list statistics. It includes key indicators, trends, and bifurcations based on case type, time bands, and specialties. 

### Project Goals
1. Track current status of patient waiting list
2. Analyze historical monthly trend of waiting list in Inpatient & Outpatient categories
3. Detailed specialty level & age profile analysis

![Image](https://github.com/user-attachments/assets/41624190-c0fe-4de0-a144-1a1ec9b57c41)

#### Summary Section
- Displays a comparison of the latest month’s wait list with the previous year's latest month.
- Highlights key wait list indicators.

#### Wait List Bifurcation (by Case Type)
- A donut chart categorizes cases into Outpatient, Day Case, and Inpatient.
- The total number of cases is segmented into percentages for each category.

#### Wait List Analysis - Time Band vs Age Profile
- A bar chart illustrates the distribution of wait times based on different age groups.
- Categories include 0-15, 16-64, and 65+ age groups.

#### Top 5 Wait List (by Specialty)
- Lists the five medical specialties with the highest patient wait numbers.

#### Monthly Trend Analysis - Day Case / Inpatient vs. Outpatients
- A time-series line chart visualizes the trends for Inpatients, Day Cases, and Outpatients from 2018 to 2021.
- Shows a growing trend in outpatient cases.

![Image](https://github.com/user-attachments/assets/3eaad3e6-2de1-4365-b532-db2a4960cbb0)

#### Detailed Grid View (Right Panel)
- Displays patient wait list details in a tabular format.
- The table is structured with columns for Day Case, Inpatient, Outpatient, and Total.

Data is grouped by specialty (e.g., Orthopaedics), age profile (e.g., 16-64, 65+, 0-15), and wait time categories (e.g., 0-3 Months, 3-6 Months, etc.).

This dashboard provides healthcare professionals with insights into patient wait times, helping optimize resource allocation and improve patient care.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, datasets are a csv files and contains two types of data categories: Inpatient(a patient tho stays in a hospital while under treatment) and Outpatient(a patient who receives medical treatment without being admitted to a hospital).
- Step 2 : Open power query editor and check data types, total number of rows, adjust column names, add breaking columns, remove spaces by trim.
- Step 3 : Append tables to one data set.
- Step 4 : Moddeling data - mapping Specialties with Specialty groups, adjusting connections manually
- Step 5 : Layout & Design workflow
- Step 6 : Add interactivity & navigation
- Step 7 : Testing all functionalities
