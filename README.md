# Hospital-Emergency-Room-Dashboard
Hospital Emergency Room Dashboard showcasing real-world healthcare KPIs, patient flow analysis, and data-driven insights using interactive visualizations.

# Project Objective
To analyze Emergency Room (ER) data and uncover insights related to:
- Patient admission trends
- ER wait time performance
- Patient demographics (age, gender)
- Department referral patterns
- Time-based trends using a 2-year calendar table

# Key Business Insights
- Nearly half of ER patients require hospital admission
- Majority of patients experience delays (wait time ≥ 30 minutes)
- Age group 30–59 years contributes the highest ER visits
- Male and female patient distribution is almost equal
- General Practice and Orthopedics receive the highest referrals
- ER workload varies significantly across months and quarters

# Tools & Technologies
- Microsoft Excel
- Power Pivot
- Power Query
- DAX (Data Analysis Expressions)
- Pivot Tables & Charts

# Dataset Overview
The dataset contains 9,217 Emergency Room patient records covering two years (2023–2024).

## Key Tables
🔹 Hospital Emergency Room Data (Fact Table)
Rows: 9,217
Columns: 13

🔹 Calendar Table (Dimension Table)
Rows: 731
Granularity: Daily
Covers 2 years for time-based analysis

## Key Columns
- Hospital ER Data
- Patient Name
- Patient Gender
- Patient Age
- Patient Race
- Department Referral
- Patient Admission Flag
- Patient Satisfaction Score
- Patient Waittime
- Age Group (Calculated)
- Patient Attend Status (Calculated)
- Date

Calendar Table
- Date
- Month
- Month Index
- Day
- Day Index
- Year
- Quarter

# Data Preprocessing
- The dataset was preprocessed using Power Query and Power Pivot by:
- Removing unnecessary and blank columns
- Handling missing department referrals
- Validating patient age and wait time values
- Creating a structured calendar table for time intelligence

# Project Workflow
🔹 Step 1: Data Loading (Excel / Power Pivot)
Imported hospital ER data into Power Pivot
Created a separate calendar table covering two years

🔹 Step 2: Data Cleaning & Validation
Performed:
- Data type validation
- Missing value checks
- Consistency checks for gender and admission status
- Structural review using Power Pivot data view

🔹 Step 3: Feature Engineering (DAX)
Age Group Calculation
Age Group =
IF([Patient Age]>=70,"70-79",
IF([Patient Age]>=60,"60-69",
IF([Patient Age]>=45,"45-59",
IF([Patient Age]>=30,"30-44",
IF([Patient Age]>=15,"15-29",
IF([Patient Age]>=5,"05-14","0-4"))))))

Patient Attendance Status
Patient Attend Status = IF([Patient Waittime] < 30, "Ontime", "Delay")

🔹 Step 4: Data Modeling
Implemented a star schema
Created relationship:
Hospital ER Data[Date] → Calendar[Date]

🔹 Step 5: Dashboard & Visualization
Created interactive dashboards with:
- KPI cards
- Bar charts
- Pie charts
- Time-series analysis

# KPIs & Analysis Performed
- Total ER Visits
- Admitted vs Not Admitted Patients
- Percentage of Patients Seen Within 30 Minutes
- Average Patient Wait Time
- Patient Distribution by Age Group
- Gender-wise Patient Analysis
- Department Referral Analysis
- Monthly & Quarterly Trends

# Analytical Findings
- Patients aged 30–59 are the most frequent ER visitors
- Delayed cases dominate, indicating process inefficiencies
- General Practice is the most burdened department
- Admission rates suggest high patient severity
- Time-based trends reveal seasonal variations in ER demand

# Conclusion
Emergency Room performance analysis shows that adult patients (30–59 years) form the core ER population, with significant delays affecting most patients. High referral volumes in General Practice and Orthopedics indicate areas requiring staffing optimization.
These insights can help hospitals:
- Reduce ER wait times
- Optimize staff allocation
- Improve patient experience
- Enhance operational efficiency
