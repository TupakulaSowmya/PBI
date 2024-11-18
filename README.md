# HR-Dashboard

## Problem Statement

The HR Dashboard provides an intuitive and data-driven approach to understanding workforce dynamics. It provides a comprehensive view of employee's helping identify improvement areas and refine HR strategies. The dashboard also analyzes trends such as attrition rates, onboarding timelines, and department-wise headcount, offering a global perspective of the workforce.

Additionally, it empowers the HR team with data on sources of hire, average employee age, and gender distribution. These insights help streamline HR processes, enhance operational efficiency, and improve overall employee satisfaction.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a Excel file.
- Step 2 : Open Power Query Editor to clean and transform your data
  1. Rename columns for clarity.

  2. Ensure date columns (e.g., Date of Hire) are correctly formatted.

  3. Remove duplicates or invalid rows.
- Step 3 : Once DataTypes are set, Close and Apply the transformation
- Step 4 : Create Mesaures. Go to the Modeling tab and create the following DAX measures
 1. Attrition: VAR a = CALCULATE(COUNT(HRDataset_v14[EmpID]), FILTER(HRDataset_v14, HRDataset_v14[Attrition]=0)) RETURN a

  2. Attrition % = ([Attrition]/[Headcount])Avg Age: Avg Age = AVERAGE(HRDataset_v14[Age])
  3. Avg Salary = CALCULATE(AVERAGE(HRDataset_v14[Salary]))
  4. Cumulative Headcount: VAR last_date= LASTDATE(HRDataset_v14[DateofHire]) RETURN CALCULATE([Headcount], ALL(HRDataset_v14[DateofHire]), HRDataset_v14[DateofHire]<=last_date)
  5.  Headcount= COUNT(HRDataset_v14[EmpID])
- Step 5 : Now the datasets are ready and we can start the visualisation.We will create 5 card visuals for Headcount, Attrition, Attrition%, Average Salary and Average Age.

![Card](https://github.com/user-attachments/assets/1f61940d-46ad-43aa-a5d2-e2f63d3e7591)

- Step 6 : Create a Clustered Bar Chart showing "Headcount" by "Department," add a Clustered Bar Chart to your report and assign "Department" to the Axis and "Headcount" to the Values field. Then, format the chart by adjusting the bar colors, resizing the text for better readability, and enabling "Data Labels" to display the headcount numbers directly on the bars. This will give a clear visual representation of the headcount distribution across departments.
- Step 7 : Visual filters (Slicers) were added for four fields named "Department", "Position", "Employee Status" & "Gender".
- Step 8 : A Stacked bar chart was also added to the report design area representing the Headcount by "MaritalStatus" and "Gender". While creating this visual, added MartialStatus on X-axis, Headcount on Y-axis and Gender on Legend.

- Step 9 : Another Stacked bar chart was also added to the report design area representing the Headcount by "RecuritmentSource". This visual represents how many employee are hired from LinkedIn, Indeed, Employee referal and other areas.

- Step 12 : Line chart visualisation was created to showcase "HeadCount" and "Cumulative HeadCount" of "DateofHire". Sort "DateofHire" on X-axis and "HeadCount", "Cumulative HeadCount" on Y-axis.
- Step 14 :  Filledmap to view the overall HeadCount in each location. Represent "State" on Location and "HeadCount" on Tooltips.

![map](https://github.com/user-attachments/assets/0117dc5b-bd62-42d8-b890-dabc8de3759f)
        
- Step 15 : The report is now ready to be  published to Power BI Service.
 
 # Report Snapshot (Power BI DESKTOP)

![screenshot](https://github.com/user-attachments/assets/516ddbae-f01e-4625-9e72-fa604ed77279)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

# HR Dashboard
Displaying #HR-Dashboard.md.txt.
