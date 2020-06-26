# School_District_Analysis

# Week 4 Challenge

In this challenge, you will use your skills using the Pandas library and Jupyter Notebook. You need to replace incorrect data in columns using logical operations with conditionals; retrieve data from DataFrames; merge, filter, slice, and sort DataFrames; and apply the groupby() function to a DataFrame. Using these methods, you will create a new analysis with the incorrect data removed.

## Background

The grades of the ninth graders at Thomas High School have been changed. While administrators do not know the full extent of this academic dishonesty, they want to uphold the standards of state testing and have turned to you for help.

After assessing the situation with the school superintendent and Maria, you decide the best approach is to:
•	Replace the ninth-grade math and reading scores from Thomas High School.
•	Keep all other data associated with the ninth-grade students and Thomas High School intact.

## Resources

Pandas & Numpy libraries
Jupyter Notebook (PythonData environment created using Python 3.7 and Anaconda)                      
csv’s provided:  schools_complete.csv, students_complete.csv

## Analysis

The iPython Notebook, PyCitySchools was developed throughout the modules for this week.  Several pandas library dataframes and functions were used to read data from the csv files, build dataframes, and acquire the requested output.  For the challenge Additionally, the pandas .loc & numpy np.nan functions were used to replace the corrupt student data with “not a number” entries.  Finally, the code was ran again with the data replaced and the results are discussed below.

## Conclusions

### How is District Summary affected?
When the Thomas High School 9th grade reading and math scores are removed from the dataset, the total schools and total students numbers are not affected.  We still use the same total number of students (39,170) to report overall averages by district.  The average math score for the district decreases from 79.0 to 78.9, but the average reading score remains the same (81.9).  The percentage of students passing math, reading, and both (overall) is reduced by ~1%.  This makes sense because there are 461 ninth grade students at Thomas High School, which is roughly 1.1% of the total 39,170 students in the district.

#### Fig. 1:  District Summary prior to removing Thomas High School 9th grade scores
![](Images/District_Summary_Original.png)

#### Fig. 2:  District Summary after removing Thomas High School 9th grade scores
![](Images/District_Summary_New.png)


### How is School Summary affected?
The School Summary dataframe changes only with regard to Thomas High School itself since we are still using the total number of students in each school to calculate the percentage of students that pass math, reading, and both at each school.  Obviously these percentages will drop precipitously for Thomas High School since roughly a quarter of the students will have no score (i.e. non-passing score) yet they will be included in the denominator of total students.

### How is Thomas High School’s performance affected when 9th grade scores are removed?
Using the original data set with the corrupted scores puts Thomas High School in the Top 5 schools in the district.  Specifically, second in the district with an overall passing percentage of 90.9.  However, when the corrupt 9th grade scores are removed from the dataset, Thomas High School drops out of the Top 5 and into the 8th slot with an overall passing percentage of 60.1.  This drop of ~30% points is to be expected since the 461 ninth grade students account for ~28% of total students at Thomas High School. Outside of retesting the 9th grade students at Thomas High School, there is no way to be sure of the true overall performance of the school.  However, further study could be done evaluating the data by replacing the 9th grade scores with overall district averages or even average scores in similar size or funded schools.  In this assignment, we were asked to simply replace the corrupt data with NaN’s.  

#### Fig. 3:  Top 5 Schools prior to removing Thomas High School 9th grade scores
![](Images/Top_5_Schools_Original.png)

#### Fig. 4:  Top 10 Schools after removing Thomas High School 9th grade scores
![](Images/Top_10_Schools_New.png)

### How does removing scores affect Math & Reading scores by grade?  
As expected, the math and reading scores by grade for all other schools are not affected when the Thomas High School 9th grade scores are removed.  This is due to how the data was grouped into the dataframe.  Nonetheless, there is now a hole in the dataset for these scores.  This can be addressed as discussed above.  

#### Fig. 5:  Math Scores by Grade
#### Before removing Thomas High School 9th grade scores                #### After 
![](Images/Math_by_grade_Original.png)                            ![](/Images/Math_by_grade_New.png)

#### Fig. 6:  Reading Scores by Grade
#### Before removing Thomas High School 9th grade scores                #### After 
![](Images/Reading_by_grade_Original.png)                         ![](/Images/Reading_by_grade_New.png) 

### By School Spending?  
Again, due to how the data was grouped for this dataframe only the bin that contains Thomas High School is affected.  Since Thomas High School’s per student budget is $638, this is the $630-644 bin.  Surprisingly, the average math & reading scores stayed the same.  Yet, because the total number of students includes the 9th grade students with no scores, the percentage of students passing math, reading, and both (overall) has dropped in this bin ~7 points.

#### Fig. 7:  Summary by School Spending prior to removing Thomas High School 9th grade scores
![](Images/School_Spending_Summary_Original.png)

#### Fig. 8:  Summary by School Spending after removing Thomas High School 9th grade scores
![](Images/School_Spending_Summary__New.png)

### By School Size?  
The same can be said for the size of the school.  Thomas High School has 1,635 so it is categorized in the Medium School Size.  Here we see a decrease of ~6 points in the percentage of students passing math, reading, and both (overall).

#### Fig. 9:  Summary by School Size prior to removing Thomas High School 9th grade scores
![](Images/School_Size_Summary_Original.png)

#### Fig. 10:  Summary by School Size after removing Thomas High School 9th grade scores
![](Images/School_Size_Summary__New.png)


### By School Type?
Lastly, Thomas High School is a Charter School.  We see a roughly 4 point drop in the percentage of students passing math, reading, and both (overall) without affecting the District Schools. 

#### Fig. 11:  Summary by School Type prior to removing Thomas High School 9th grade scores
![](Images/School_Type_Summary_Original.png)

#### Fig. 12:  Summary by School Size after removing Thomas High School 9th grade scores
![](Images/School_Type_Summary__New.png)



