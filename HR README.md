# Powerbiproject
End to end data analysis and dashboard creation
							POWER BI
---------------------------------------------------------------------------------------------------------------------------------------------
						HR ANALYTICS DASHBOARD
---------------------------------------------------------------------------------------------------------------------------------------------
							OBJECTIVES
---------------------------------------------------------------------------------------------------------------------------------------------
>>KPI Cards(5)
	-Overall Employees
	-Attrition Count(Yes)
	-Attrition Rate
	-Active Employee
	-Average Age
>>Charts(5)
	1.Pie Chart
		-Department Wise Attrition
	2.Frequency Chart
		-No of Employee by Age Group
		-Gender,Age Band
	3.Matrix/HeatMap Chart
		-Job Satisfaction Rating
		-Job Roles
	4.Bar Chart
		-Education Field wise Attrition
		-Education Filed
	5.Multiple DONUT Charts(5)
		-Attrition Rate by Gender for different Age Group
		-Donut Chart 1 Under-25
		-Donut Chart 2 25-34
		-Donut Chart 3 35-44
		-Donut Chart 4 45-54
		-Donut Chart 5 Over 55
>>Slicer/Filter in the form of Buttons
	-Associate Degree
	-Bachelor's Degree
	-Doctorial Degree
	-High School
	-Master's Degree
----------------------------------------------------------------------------------------------------------------------------------------------
						  POWER BI DASHBOARD	
----------------------------------------------------------------------------------------------------------------------------------------------
							STEP-1
----------------------------------------------------------------------------------------------------------------------------------------------
>>Open the Hrdataset in excel and analyis the complete data
>>Import Hr Dataset file in Powerbi
>>Open Data View Page
	>>If you See Headers as Column1,Column2,Column3,....,We cant Design Dashboards with this data error
	>>Open the TRANSFORM DATA (Power Query Editor)
		-Use first Row as Header(Column Header Name Changes Automatically)
		-Home Tab-Close & Apply
	>>Open the Report View Page
		-Click VIEW BUTTON -Page View -Fit to Page
----------------------------------------------------------------------------------------------------------------------------------------------
							STEP-2
----------------------------------------------------------------------------------------------------------------------------------------------
>>VISUALIZATION
---------------------------------------------------------------------------------------------------------------------------------------------
						      KPI CARDS
----------------------------------------------------------------------------------------------------------------------------------------------
	1.KPI CARD -OVERALL EMPLOYEES
----------------------------------------------------------------------------------------------------------------------------------------------
		>>Build Visuals
		>>Select KPI Card
		>>FIELDS-Hr Data -Select Employee Count 
		>>ADD Background Image
			-Format Page-Canvas Background-Browse(Gradient BAckground Wallpaper)
			-Transperancy - 8%
			-Image Fit - Fit
		>>Select Visual(KPI Card)
			>>Click Format Page - General-Title
				-Title (on)-Text-OVERALL EMPLOYEES
				-Alligment-Center
				-Font-Segio ui Semibold
			>>Format Page-General-Properties
			     >>Size
				-Height-110
				-Width-240
			>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
			>>Format Page-Visuals-callout Value
				-Background color-White
			>>Format Page-General-Title
				-Text color -Light White
			>>Format Page-General-Effects-Visual Border
				-Visual Border on
				-Color -Gradient Purple color (default more colors)
				-Rounded corners-15%
--------------------------------------------------------------------------------------------------------------------------------------------
	2.KPI CARD-ATTRITION
--------------------------------------------------------------------------------------------------------------------------------------------
		>>Copy Paste First KPI Card
		>>Click Format Page - General-Title
				-Title (on)-Text-ATTRITION
		>>Home Button/Tab - Go to Transform Data
		>>Transform Data(Power query Editor)

		/**Attrition Yes or No = Yes Means The Employee has left the Company
				       = No Means The Employee Still working in company**/

		>>Attrition First Column
			-We have to find How many yes is there in attrition
			>>Add in Column 
				-Conditional Column
				-New Column Name - Attrition count
				-If-Attrition-EQUALS-Yes-1-Else-0 (Click ok)
				-Home-CLOSE & APPLY
				-Data View we can see -Attrition column
				-Select attrition column and change -Format- WHOLE NUMBER
			/**Without Changing Format Text to Whole Number we cant see the results in KPI Card**/
		>>select KPI Card-Fields-Attrition Count
			you can see the results - 237
--------------------------------------------------------------------------------------------------------------------------------------------
	3.KPI CARD-ATTRITION RATE
--------------------------------------------------------------------------------------------------------------------------------------------
		>>Copy paste First KPI CARD
		>>Click Format Page - General-Title
				-Title (on)-Text-ATTRITION Rate(16.12%)
		>>ATTRITION RATE = SUM OF ATTRITION / SUM OF OVERALL EMPLOYEES (237/1470=0.1612)
		>>New Measure
			-ATTRITION Rate = SUM(['HR data'[Attrition Count])/SUM(['HR data'[Employee Count])
			-Click Check right ok
			-Select Fields-Hr data-Attrition Rate
			-Format-Percentage
--------------------------------------------------------------------------------------------------------------------------------------------
	3.KPI CARD - Active Employees
--------------------------------------------------------------------------------------------------------------------------------------------
		>>Copy paste First KPI CARD
		>>Click Format Page - General-Title
				-Title (on)-Text-Active Employees
		>>New Measure
			-Active Employees = SUM('HR Data'[Employee Count]) - SUM('HR Data'[Attrition Count])
			-Click check Right ok
			-Select Fields-Hr data-Active Employees
-----------------------------------------------------------------------------------------------------------------------------------------
	4.KPI CARD - Average Age
-----------------------------------------------------------------------------------------------------------------------------------------				
		>>Copy paste First KPI CARD
		>>Click Format Page - General-Title
				-Title (on)-Text-Average Age 
		>>Build Visuals
			-Fields -Average of age	
		>>Format Visuals
			-visuals-Callout Value-Value Decimal Places
-----------------------------------------------------------------------------------------------------------------------------------------
							   CHARTS
-----------------------------------------------------------------------------------------------------------------------------------------
	1.PIE CHART
-----------------------------------------------------------------------------------------------------------------------------------------
		>>Pie Chart
			-Select Department(hrdata field) into LEGEND(build Visual)
			-Select Attrition Count(Hr Data Field) into Values(Build Visual)
		>>Format Page -General-Properties
		     >>Size
			-Height -260
			-Width - 385
		>>Format Page -General-Title
			-Title on-Text -DEPARTMENT WISE ATTRITION
			-Alligment-Centre
		>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
		>>Format Page-General-Effects-Visual Border
				-Visual Border on
				-Color -Gradient Purple color (default more colors)
				-Rounded corners-15%
		>>Format Page-General-Title
				-Text color -Light White
		>>Format Page-Visuals-Legend
				-Text color - White
		>>Format Page-Visuals-Value
				-Text color -White
-------------------------------------------------------------------------------------------------------------------------------------------
	2.Stacked Column Chart
-------------------------------------------------------------------------------------------------------------------------------------------
		>>Select Visuals -Stacked Column Chart
		>>Fields-Hr Data
			-Agee Band on  X-axis
			-Employee Count on Y-axis
			-Gender on Legend
		>>Format Page -General-Title
			-Title on-Text -No of Employees By age Group
		>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
			>>Format Page-Visuals-callout Value
				-Background color-White
			>>Format Page-General-Title
				-Text color -Light White

			>>Home Button/Tab - Go to Transform Data
			>>Transform Data(Power query Editor)
		>>Add in Column 
				-Conditional Column
				-New Column Name -Sort Age
				-If-Age Band-EQUALS-Under25-1
				-If-Age Band-EQUALS-25-34-2
				-If-Age Band-EQUALS-34-44-3
				-If-Age Band-EQUALS-44-54-4-Else-5
				-Home-CLOSE & APPLY
				-Data View we can see -Sort Age column
				-Select Sort Age column and change -Format- WHOLE NUMBER
			>>Select Cf_Age Band
			>>column tools Button
				-Sort by column -Sort Age
			>>Select Chart 
				-Three dots... click Sort axis-Cf_Age Band
				--Three dots... click SortSegment-Sort Ascending order
-------------------------------------------------------------------------------------------------------------------------------------------
	3.Matrix Chart /Heat Map
-------------------------------------------------------------------------------------------------------------------------------------------
		>>Select Matrix Chart on Visuals
		>>Select the Fields-Hr Data
			-Job Role on Rows
			-Job Satisfaction on Column
			-Employee Count On Values

		>>Format Page -General-Title
			-Title on-Text -Job satisfaction Rating
		>>Gridlines
		>>Horizontal Lines
		>>border lines
		>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
			>>Format Page-Visuals-callout Value
				-Background color-White
			>>Format Page-General-Title
				-Text color -Light White
			>>Format Page-General-Effects-Visual Border
				-Visual Border on
				-Color -Gradient Purple color (default more colors)
				-Rounded corners-15%
----------------------------------------------------------------------------------------------------------------------------------------
	4.Bar chart
----------------------------------------------------------------------------------------------------------------------------------------
		>>Select Bar Chart in Visuals
		>>Select the Fields-Hr Data
			-Education Field on Y-Axis
			-Attrition count on X-Axis
		>>Format Page -General-Title
			-Title on-Text -Education Field Wise Attrition
		>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
			>>Format Page-Visuals-callout Value
				-Background color-White
			>>Format Page-General-Title
				-Text color -Light White
------------------------------------------------------------------------------------------------------------------------------------------
	5.Donut Chart
------------------------------------------------------------------------------------------------------------------------------------------
		>>Select Donut Chart in Visuals	
		>>Fields-Hr Data
			-Gender on  Legend
			-Attrition Count on Values
			-Cf_Age Band on Details
		>>Format Page -General-Title
			-Title on-Text -Under25
		>>Format Page -Visuals
			-Rotation -30%
	Text Box -Attrition Rate by gender for different Age Groups
		>>Copy paste Donut Chart 4
			>>Format Page-General-Efects
			     >>background
				-Color-More colors-#9664A0
				-Transperancy-75%
			>>Format Page-Visuals-callout Value
				-Background color-White
			>>Format Page-General-Title
				-Text color -Light White
-----------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------------ 
			
						
