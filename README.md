# Power-Query-Data-Transformation-Guide
This project demonstrates how to preprocess raw data using Power Query in both Excel and Power BI. The goal is to clean, transform, and prepare data for analysis and reporting.

🔍 Overview
Power Query is a powerful data transformation engine that enables you to import raw data, clean it, and prepare it for further analysis—all without altering the original file. The steps below walk through a practical example, from initial import to final data analysis.

📂 Project Contents
original-data.xlsx — The raw, uncleaned data file

transformed-data.xlsx — The file with Power Query transformations applied

This README.md file

🧰 Steps to Transform Data Using Power Query
✅ Step 0: Import Data & Remove Unnecessary Content
Go to the Data ribbon in Excel or Power BI and click Get Data.

Choose your source (e.g., Excel file).

Load the data and select Transform Data.

Use:

Choose Columns: Unselect all and choose only the necessary columns.

Remove Rows > Remove Top Rows: Delete unnecessary header/info rows.

Use First Row as Headers: Promote your actual headers.

⚠️ All transformations are non-destructive to the original Excel file.

🧹 Step 1: Dealing with Blank Values
Use the dropdown in the column headers to deselect null or blank values.

🔁 Step 2: Removing Duplicates
Identify a unique field (e.g., Email) that can serve as a unique key.

Right-click the header and select Remove Duplicates.

🆔 Step 3: Generating ID Values
Go to the Add Column tab.

Select Column from Examples.

Type a few examples of the ID pattern you want.

Power Query will autofill the rest. Click OK.

Rename the column as desired.

📅 Step 4: Course Term Calculation from Registration Date
Ensure Registration Date column is of type Date:

Right-click column > Change Type > Date.

Use Add Column > Conditional Column:

Condition: If date is before 15-Dec-2022, then output 01-Feb-2022, else 01-Apr-2022.

Change the new column's type to Date.

💰 Step 5: Fee Status Categorization
Ensure Fee Status column is of type Number.

Add a Conditional Column:

If value = null, then "Not Paid"

If value = 500, then "Fully Paid"

Else, "Partly Paid"

📊 Step 6: Data Analysis in Pivot Table
Click Close & Load to load transformed data into Excel.

Use Table Tools > Summarize with Pivot Table:

Rows: Course

Columns: Values

Values: Fee and Email

🔁 Auto-Refresh Transformed Data
If changes are made in the original Excel file:

Right-click on the transformed query table.

Select Refresh to automatically update with the latest data.

📺 Tutorial Reference
This walkthrough is based on the video:
Power Query Data Transformation Guide (YouTube)

📌 Notes
Power Query transformations do not alter the source file.

This guide is applicable in both Excel and Power BI environments.
