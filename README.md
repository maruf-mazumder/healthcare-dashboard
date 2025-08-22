# A comprehensive, step-by-step Power BI project building a healthcare dashboard from raw data to actionable insights.

## Problem Statement
This healthcare dashboard helps hospital administrators and healthcare providers better understand patient waiting times and service efficiency. It enables stakeholders to monitor the status of inpatient and outpatient waiting lists, identify trends, and pinpoint areas requiring improvement. By analyzing key metrics such as average and median waiting times across specialties and age profiles, the dashboard highlights bottlenecks and inefficiencies in patient flow.

With a significant portion of patients experiencing long waiting times, especially in certain specialties, the dashboard reveals critical areas where service improvements are needed. Additionally, by tracking monthly trends and waitlist variations, healthcare providers can focus on reducing excessive delays and optimizing resource allocation to enhance patient satisfaction and care quality.


### Key terms used
- Inpatient Cases: Inpatient cases refer to patients who are admitted to the hospital for at least one night for treatment or surgery. 
- Daily Cases: Patients who are admitted and discharged within the same day 27 Outpatient Cases 
- Outpatient cases refer to patients who receive medical treatment or undergo procedures without being admitted to the hospital.


### Steps followed 

- Step 1: Load Data into Power BI Desktop
The dataset consists of multiple CSV files, each representing a year's patient waitlist data, separated into two folders for inpatient and outpatient categories. These files were imported into Power BI Desktop using the folder connector, which allowed combining and consolidating all files within each category into a single table. Subsequently, the inpatient and outpatient tables were transformed and appended together to create a unified dataset named ALL_DATA for further analysis.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4: During data inspection, it was found that the column named "Specialty_Name" was labeled as "Specialty" in the inpatient folder, which was corrected for consistency. Additionally, all CSV files were cross-checked to ensure they contained the same number of columns. It was also observed that the outpatient dataset lacked a "Case_Type" column, which was added with the value "Outpatient" to align with the inpatient data structure.

 
- Step 6 : The background was designed using MS Powerpoint.
 
- Step 8 : Visual filters (Slicers) were added for four fields named "Archive_Date", "Case_Type", "Specialty_Name" .
        <img width="1002" height="137" alt="Image" src="https://github.com/user-attachments/assets/91f8add3-6035-4548-a654-3d8a049387b4" />

- Step 9 : Two card visuals were added to the canvas, one representing latest month waiting list & other representing waiting list for the same month for the previous year.



         Latest Month Wait List = CALCULATE(SUM(All_Data[Total]) , All_Data[Archive_Date] = MAX(All_Data[Archive_Date]))  + 0

        PY Latest Month Wait List = CALCULATE(  SUM(All_Data[Total]), FILTER(
        All_Data, 
        All_Data[Archive_Date] = EDATE(MAX(All_Data[Archive_Date]), -12) ) ) + 0 
     
- step 13: A Dynamic filter allows us to choose the type of metric we want to see in the visuals (Average/Median)

         Dynamic Title = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average", "Key Indicators - (Patient Wait List Average)","Median", "Key Indicators - (Patient Wait List Medain)" )



- Step 10 : A stacked column chart was also added to the report design area representing  waiting list for different age groups on different month range in the year, in a descending order of the average/Median waiting list .


  <img width="442" height="345" alt="Image" src="https://github.com/user-attachments/assets/734f4419-718c-4ded-9db3-51eb2d1b6eb0" />


- Step 11 : Donut Chart represents distribution of waiting list for different case types . 
  <img width="445" height="361" alt="Image" src="https://github.com/user-attachments/assets/05dfc9ab-42a9-42bd-82ff-3d67b87fe6a5" />


- step 12: Top Waiting list for different specialty was added on the right most side . 
  <img width="445" height="361" alt="Image" src="https://github.com/user-attachments/assets/85921516-58fb-4630-a6f2-2b609ca2efbc" />
 

 

- Step 13 : In the report view, under the 3 dynamic charts tab, two more dynamic line charts boxes were added to the canvas, in one of them total wait list is shown for inpatient and day case patients and the other one represents the total waiting list for outpatients . Only Specialty filter and the date range is applicable on them. An information icon button letting us visit the detai page. A back button allowing us to return back to the main report page.
  <img width="1312" height="307" alt="Image" src="https://github.com/user-attachments/assets/6186121f-12c9-49c3-aacc-b394e408c4cf" />



        
- Step 15 : In the detailed View the total waitlist for Day case, In patient and Out patient was presented in tabular form for different specialty name on date by date basis.
Filter criteria can be selected from the left side ,i.e- Archive_Date, Case_Type, Specialty_Name, Age_Profile, Time_Brands

  <img width="882" height="602" alt="Image" src="https://github.com/user-attachments/assets/c2c4ca16-9be2-486a-89fa-4035864c1dc3" />


- Step 15: Another View "Drilldown" was created as a tooptip for the 2 line charts in the Summary Page. Total wait list is visible there for all Specialty groups with the total number of waitlist on the top .
- <img width="436" height="735" alt="image" src="https://github.com/user-attachments/assets/ea8b1ece-c27a-4ebc-8838-c496f793cc63" />


### Main Dashboard View
<img width="1051" height="712" alt="Image" src="https://github.com/user-attachments/assets/1536d709-b2fc-4128-8ca8-59cc73003768" /> 
