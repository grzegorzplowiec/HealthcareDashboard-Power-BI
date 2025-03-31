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

- Step 1 : Loaded data into Power BI Desktop, datasets are a csv files and contains two types of data categories: Inpatient(a patient tho stays in a hospital while under treatment) and Outpatient(a patient who receives medical treatment without being admitted to a hospital).
- Step 2 : Opened power query editor and checked data types, total number of rows, adjusted column names, add breaking columns, removed spaces by trim.
- Step 3 : Appended tables to one data set.
- Step 4 : Moddeling data - mapping Specialties with Specialty groups, adjusting connections manually.
- Step 5 : Layout & Design workflow.
- Step 6 : Created dynamic fields to count latest month waiting patients and same month previous year waiting patients.

Following DAX expressions was written:
        
        Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date] = MAX(All_Data[Archive_Date])) + 0

        PY Latest Month Wait List = CALCULATE(SUM(All_Data[Total]),All_Data[Archive_Date]= EDATE(MAX(All_Data[Archive_Date]),-12)) + 0

- Step 7 : Created new table to storage required measures (Average and Median).
- Step 8 : Added slicer using table with measures.
- Step 9 : New measure was created to find Average and Median of Total waiting list.

Following DAX expressions was written:

        Average Wait List = AVERAGE(All_Data[Total])

        Median Wait List = MEDIAN(All_Data[Total])

- Step 10 : New measure was created to switch between Average and Median measures.

Following DAX expressions was written:

        Avg/Med Wait List = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average",[Average Wait List],"Median",[Median Wait List])

- Step 11 : New measure was created to change title of the dashboard.

Following DAX expressions was written:

        Dynamic Title = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average","Key Indicators - Patient Wait List (Average)","Median","Key Indicators - Patient Wait List (Median)")

- Step 12 : New measures was created to display a caption when there is no data on the charts
    
Following DAX expressions was written:
        
        NoDataLeft = IF(ISBLANK(CALCULATE(SUM(All_Data[Total]),All_Data[Case_Type]<>"Outpatient")),"No data for selected criteria","")

        NoDataRight = IF(ISBLANK(CALCULATE(SUM(All_Data[Total]),All_Data[Case_Type]="Outpatient")),"No data for selected criteria","")
- Step 13 : Created custom tooltip chart shows split of specialty groups for particular month
![Image](https://github.com/user-attachments/assets/5e542806-74f6-407a-a9bf-c297df03cb99)

- Step 14 : Created background for dashboard.
- Step 15 : Applied visual changes to charts and formatted numbers.
- Step 16 : Add interactivity & navigation
- Step 17 : Testing all functionalities
