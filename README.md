📌 Project Overview

This project is a comprehensive end-to-end Data Analytics solution built with Microsoft Power BI. It processes and visualizes Human Resources data to extract actionable insights regarding employee retention, demographics, and recruitment. The dashboard empowers HR stakeholders to track core KPIs, analyze attrition trends over time, and utilize an interactive drill-through feature for granular employee-level data.

💼 Business Value & Impact (How this helps the company)

Workforce Retention & Attrition Tracking: Provides executive-level visibility into Total Headcount and Attrition Rates, allowing management to identify alarming turnover trends and take proactive retention measures.

Demographic & Diversity Insights: Visualizes employee distribution across Age Buckets, Gender, and Marital Status, helping HR teams ensure diversity and tailor employee engagement programs.

Recruitment Strategy Optimization: By tracking headcount across various Recruitment Sources (e.g., LinkedIn, Indeed, Referrals), the talent acquisition team can identify the most effective hiring channels and allocate recruitment budgets efficiently.

Granular Reporting: The interactive drill-through capability allows managers to seamlessly transition from a high-level departmental overview to a detailed tabular view of individual employees without cluttering the main dashboard.

🛠️ Technical Challenges & Solutions

During the development of this dashboard, several data engineering and modeling challenges were successfully resolved:

Data Type Casting & Age Calculation:

Problem: The raw dataset provided dates (Date of Birth, Date of Hire) as standard Text, and lacked a direct 'Age' metric.

Solution: Utilized Power Query Editor to transform and cast column data types to Date. Authored a custom DAX calculated column Age = DATEDIFF('HRDataset_v14'[DOB], TODAY(), YEAR) to dynamically calculate employee ages.

Custom KPI Creation via DAX:

Problem: Crucial business metrics like 'Attrition' and 'Attrition Rate' were not explicitly available in the raw data.

Solution: Authored custom Data Analysis Expressions (DAX) measures. Created conditional counts (e.g., CALCULATE(COUNT(EmpID), EmploymentStatus <> "Active")) to find attrition, and divided it by total headcount to generate dynamic percentage-based KPIs.

Data Categorization for Visual Clarity:

Problem: Plotting individual ages on a chart creates visual clutter and provides little analytical value.

Solution: Implemented a DAX SWITCH function to group continuous age data into distinct categorical 'Age Buckets' (e.g., 26-35, 36-45, 55+), enabling the creation of a clean, insightful Donut Chart.

Advanced Interactive Navigation (Drill-Through):

Problem: Stakeholders needed to see specific employee details (Name, Position, Salary) for a particular department without leaving the dashboard environment.

Solution: Engineered a dedicated 'Detailed View' drill-through page. Configured page settings to accept 'Head Count' and 'Department' as drill-through filters, allowing users to right-click a visual on the main page and instantly generate a filtered tabular report.

📂 Repository Contents

HR Dashboard Analytics.pbix: The core Power BI dashboard file containing the data model, DAX queries, and interactive visuals.

HR Dashboard Analytics.pdf: An exported PDF version of the dashboard for quick non-interactive viewing.

HR Dashboard Analytics.png: High-resolution screenshot of the Main Dashboard page.

HR Dashboard Detailed View.png: High-resolution screenshot of the Drill-Through (Detailed View) page.

HR Dashboard Analytics.xlsx: The raw dataset used for this analysis.

👨‍💻 Author

Bayzid Mostak




Data Analyst & Visualization Expert

LinkedIn

GitHub

Note: Please download the .pbix file and open it in Power BI Desktop to interact with the dashboard, slicers, and drill-through features.
