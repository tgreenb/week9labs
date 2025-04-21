# Instructor-led Lab: Descriptive Statistics

In this assignment you will practice implementing statistical approaches in Python. You will use the datasets you previously made use of in the Week 7 Independent lab. 

## Context

Your administrator was pleased with your work in creating subsets of the hospital data. Recall, you belong to a team assigned to assess the condition of the healthcare system in California. You currently work in the Information Systems department for a consulting firm working with the state government agency that oversees the healthcare system in California. The data you used included two files (see the two tables for metadata): 
* Data for 61 hospitals in the file [CaliforniaHospitalData.csv](/data/CaliforniaHospitalData.csv)
* Personnel data containing employee information within the file [CaliforniaHospitalData_Personnel.txt](/data/CaliforniaHospitalData_Personnel.txt)

This first table provides the variables in the hospital data.

| Variable | Description |
|:---|:---|
| HospitalID | The primary key of each hospital |
| Name | The legal name of the hospital |
| Zip | Zipcode where the hospital is located |
| Website | The url for the hospital's website |
| TypeControl | Indicates the primary managing entity of the hospital |
| Teaching | Indicates teaching status |
| DonorType | This field indicates the most prominent group of donors |
| NoFTE | Number of full-time employees registered at the hospital |
| NetPatRev | Net patient revenue |
| InOperExp | Estimate of the inpatient operating costs |
| OutOperExp | Estimate of the outpatient operating costs |
| OperRev | Operating revenue of the hospital |
| OperInc | Operating Income is the operating revenue less the operating expenses |
| AvlBeds | The number of available beds in the hospital |

This second table provides the data for the personnel data.

| Variable | Description |
|:---|:---|
| HospitalID | The foreign key of the hospital where position is held |
| Work_ID | Primary key of the personnel |
| LastName | The last name of the personnel |
| FirstName | First name of the personnel |
| Gender | Gender of the individual |
| PositionID | The foreign key for the position held |
| PositionTitle | The title of this position |
| Compensation | The annual amount the position is compensated for service |
| MaxTerm | The maximum number of years an individual can serve in this position |
| StartDate | The beginning of service for this position |


## Prep Data and Add A New Record
Your purpose for this assignment is to conduct a descriptive analysis on the data as a precursor to model building. You will use Python to perform your analysis. Merge the two data files. Remove the following columns of data:
* `Work_ID`
* `PositionID`
* `Website`

Select one of the existing hospitals in the data and create a new position for yourself. Put in your first name and last name. Put today's date as the start date. Select one of the positions as shown in the table below and fill out the data accordingly. Fill in the rest of the columns as you choose. You should have one new row of data.

Output the DataFrame in your notebook.

| PositionTitle | Compensation | MaxTerm |
|:---|---:|:---:|
| Regional Representative | 46978 | 4 |
| State Board Representative | 89473 | 3 |
| Acting Director | 248904 | 8 |
| Safety Inspection Member | 23987 | 2 |

After merging the data files together, convert any date-time columns into a datetime data type. Ensure object data (e.g., `TypeControl`, `Teaching`, `DonorType`, `Gender`) has the categorical data type. 

## Descriptive Statistics

Please produce the following summary statistics:
* Provide a summary of the mean, median, minimum value, and maximum value for each numeric variable.
* Provide summary statistics of your text variables.
* Provide summary statistics of your categorical variables.

Create some visuals to explore the data:
* Create histograms of the following variables: `NoFTE`, `NetPatRev`, `InOperExp`, `OutOperExp`, `OperRev`, `OperInc`, and `AvlBeds`.
* Create scatterplots of the following variables using *net patient revenue* as the target variable (i.e. place it on the *y*-axis): `NoFTE`, `InOperExp`, `OutOperExp`, `OperRev`, `OperInc`, and `AvlBeds`.
  * Describe the linearity and trend of each plot you created.
* Create a boxplot and assess the lack or presence of outliers for the following variables: `NoFTE`, `NetPatRev`, `InOperExp`, `OutOperExp`, `OperRev`, `OperInc`, and `AvlBeds`. You may need to split the variables up due to the range of values in the data (like we did in the tutorial).
  * Choose three variables and create a QQ plot, providing your assessment of the normality.
  * Perform a Shapiro-Wilk test of those three variables; do your results coincide with the QQ plots?