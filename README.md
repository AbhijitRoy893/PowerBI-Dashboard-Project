🚧 Road Accident Analysis Dashboard | Power BI

An interactive Power BI dashboard that analyzes road accident and casualty data to uncover patterns in severity, road conditions, location, vehicle type, area type, and lighting conditions — supporting data-driven road-safety planning.
📌 Overview

Road accident datasets contain large volumes of records that are difficult to interpret in spreadsheets. This dashboard converts raw data into actionable insights, helping identify high-risk areas, trends, and contributing factors behind road accidents.
## 📷 Dashboard Preview

![Dashboard](dashboard-preview.png)

❓ Business Problem

This project answers key questions such as:


How many accidents and casualties occurred in 2022?
Did casualties increase or decrease compared with the previous year?
Which accident severity category has the highest number of casualties?
Which road type is most associated with casualties?
Are casualties higher in urban or rural areas?
Do more casualties occur during daylight or dark conditions?
Which months show higher accident activity?
Which locations should be prioritized for safety interventions?



📊 Key Insights

MetricValueTotal casualties (2022)~195.7KYear-over-year change~11.9% decreaseUrban area casualties~61.9%Daylight casualties~73.8%Single carriageway casualties~145K


Casualty patterns compared month-wise between 2021 and 2022
Severity breakdown across Fatal, Serious, and Slight categories



ℹ️ Values may vary depending on the source data, data cleaning rules, filters, and refresh date.




✨ Dashboard Features


KPI cards for Total Casualties, Total Accidents, and Accident Severity
Year-over-Year (YoY) comparison
Monthly casualty trend comparison for 2021 vs 2022
Casualties by Road Type
Casualties by Vehicle Type
Casualties by Urban vs Rural Area
Casualties by Light Conditions
Geographic accident hotspot analysis using map visuals
Interactive slicers and filters



📈 Visuals Used

VisualPurposeKPI CardsShow key metrics at a glanceLine / Area ChartCompare monthly casualties for 2021 and 2022Horizontal Bar ChartCompare casualties by road typeDonut ChartsShow proportional distribution by area and light conditionMap VisualIdentify accident hotspots by locationSlicersFilter the dashboard interactively


🗂️ Dataset Fields


Accident_Index
Accident Date
Number_of_Casualties
Accident Severity
Vehicle Type
Road Type
Urban_or_Rural_Area
Light Conditions
Latitude
Longitude
Location
Year
Month



🛠️ Data Preparation

Performed in Power Query / Power BI:


Imported the road accident dataset
Checked and corrected data types
Removed duplicate and invalid records
Handled missing values where required
Created a Date table for time intelligence
Standardized categorical values such as severity, road type, and light conditions
Created DAX measures for KPIs and comparisons
Built visuals and added slicers for user interaction



🧮 DAX Measures

Total Casualties

daxTotal Casualties = SUM(Data[Number_of_Casualties])

Total Accidents

daxTotal Accidents = DISTINCTCOUNT(Data[Accident_Index])

Current Year Casualties

daxCY Casualties = TOTALYTD([Total Casualties], 'Date'[Date])

Previous Year Casualties

daxPY Casualties = 
CALCULATE(
    [CY Casualties],
    SAMEPERIODLASTYEAR('Date'[Date])
)

Year-over-Year Change %

daxYoY Change % = 
DIVIDE(
    [CY Casualties] - [PY Casualties],
    [PY Casualties]
)

Serious Casualties

daxSerious Casualties = 
CALCULATE(
    [Total Casualties],
    Data[Severity] = "Serious"
)


📁 Project Structure

Road-Accident-Analysis-PowerBI/
│
├── README.md
├── Road Accident Analysis Dashboard.pbix
├── data/
│   └── road_accident_data.xlsx
├── images/
│   └── dashboard-preview.png
└── docs/
    └── project-report.pdf


▶️ How to Run the Project


Download or clone this repository.
Install Power BI Desktop.
Open the .pbix file.
If prompted, update the data source path:

Go to Transform Data
Select Data Source Settings
Update the source file location



Click Refresh.
Use the report slicers to explore the dashboard.



💡 Recommendations


Improve safety infrastructure on single carriageways.
Focus road-safety campaigns and traffic management efforts in urban areas.
Use monthly trend data for seasonal awareness campaigns and enforcement planning.
Improve signage, visibility, lighting, and pedestrian safety at high-risk locations.
Use map-based hotspots to prioritize local road-safety interventions.
Increase awareness for private vehicle and two-wheeler safety.



🧰 Tools and Technologies


Power BI Desktop
Power Query
DAX
Microsoft Excel / CSV
Data Visualization



👤 Author

Abhijit Roy
LinkedIn · GitHub


📄 License

This project is intended for educational and portfolio purposes. Please verify the original dataset license before redistributing the data.


⭐ If You Like This Project

Give this repository a ⭐ on GitHub!
