Data cleaning =COUNTIF('Hospitalisation Details'!A2:'Hospitalisation Details'!A2344, "?") for missing 2) Fill in the missing values of ‘month’ with Sep and ‘year’ with its average rounded to the nearest integer. Press Ctrl + H (Find and Replace). Avg Year 1982.841656 1983 replaced two columns with 1983

Determine the most frequently occurring values in the ‘smoker’, 'Hospital tier' and 'City tier' columns, and fill in the missing values accordingly. a) Replace the ? In Smoker with unknown Yes 488 488 No 1845 1845 Most frequesnt value in Smoker is " No" b) Hospital tier 309 tier 1 309 first replace the ? With null then replace it to mode(most frequent ) 1340 tier 2 1339 694 tier 3 694 Replaced ? With tier 2 c) City tier 734 tier 1 734 813 tier2 812 796 tier 3 796

 Data transformation
If any 'State ID' values are missing, consider filling them with 'Unknown' or using another appropriate strategy. 0 missing values 2 R1011 2319 2319 R1012 2336 Replace the missing values with missing Unknown

Check for inconsistencies in the 'Heart Issues' and 'smoker' columns and propose corrective actions if necessary.

Capitalize each word and '?;' Replaced to unknown

Create a new column named “Weight Status” that categorizes BMI into different categories as below:

IFS([@BMI]<18.5, "Underweight ", [@BMI]<24.9, "Normal Weight", [@BMI]<29.9, "Overweight ", TRUE, "Obesity")

Create a new column named “Diabetes Status” and fill it as per the information given below:

IFS([@HBA1C]<5.7, "Normal", [@HBA1C]<6.4, "Prediabetes ", TRUE, "Diabetes")

Merge ‘year’, ‘month’ and ‘date’ columns in the “Hospitalization Details” Table into one column named ‘Date of Birth’ and format it in ‘DD-MMM-YYYY’ custom format.

   Date	([@year],MONTH("1-"&[@month]),[@date])								then format cells date -DD-MMM-YYYY				
Calculate the ‘Age’ of each customer based on their ‘Date of Birth’ and the date of collection of the dataset, which is 8thJune 2023.

 DATEDIF([@[Date of Birth]], DATE(2023,6, 8),"Y")						change the data type as NUMBER			 FORMAT		
Format ‘charges’ column as currency ($). Change the datatype to Currency

Health Care VLOOKUP([@[Customer ID]],'Hospitalisation Details'!A:E,5,FALSE)
