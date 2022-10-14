# School_District_Analysis-
Aggregate data and showcase trends in school performance.

## Project Overview 
In this project, we are going to assist Maria, a chief Data Scientist for a city school district, to complete the school district analysis. To do that we need to do the following tasks: 
1. Collect the student data into a DataFrame.
2. Prepare a cleaned version of the DataFrame.
3. Summarize key pieces of the data.
4. Drill down into the data to analyze specific subsets.
5. Compare and contrast the data through grouping and aggregation functions.
6. Write an analysis of the results.

### Purpose 
The aim of this project is to aggregate the data and showcase trends in school performance.

## Resources 
- Data Source: new_full_student_data.csv
- Software: Python 3.7.13, Conda 4.14.0, Jupyter Notebook

## Analysis of Data 
The first major piece of our code is to import required dependencies: <br /> 
```import pandas as pd``` <br /> 
```import os``` <br /> 
Now we can start our analysis in order to complete our task. <br /> 

To check the full code please go to the following link: https://github.com/MireyNM/School_District_Analysis-/blob/main/Student_Data_Challenge_Starter_Code/Unsolved/Student_Data_Challenge_Starter_Code.ipynb

1.  **Collect the student data into a DataFrame.** <br /> 
To collect the student data, we need to import it into a structure that Python and Pandas can work on. Therefore, we have created a file path, to the external file ```new_full_student_data.csv``` saved in the "Resources" folder. And we used ```pd.read_csv``` to be able to read the file. <br />

To verify that the data was properly imported we have used the ```head()``` function to display the first 5 rows of our data (See Fig.1) 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190835451-34173002-aa7b-4af3-be42-d7bda1f62c35.png">
</p>
<p align = "center">
Fig.1 - Display the first 5 rows of the data.
</p>

In this part I would suggest to use the ```tail()``` function in order to take a general idea about the data. This function will display the last 5 rows, hence we will be able to know how many rows we are working with. (How big is our data)


2. **Prepare a cleaned version of the DataFrame.** <br /> 
To prepare the data and clean it we have done the following:
- Checked for rows that have ```Nan``` (or missing) values and duplicated rows in order to remove them. 
- Checked the data types of each column. In this step, we found that the grade column is considered as object because the grade values have the "th" suffix. Therefore, we have removed it and changed the grade column type to integer in order to be able to use the values of this column in our statistics analysis. 

3. **Summarize key pieces of the data.**<br /> 
In this part, we have used the ```describe()``` function to summarize the statistics for the Student Data Frame (See Fig.2). <br /> 
Moreover, we have used the ```mean()``` function to display the average of math score and the ```min()``` function to store the minimum value of the reading score. <br /> 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190835806-a47ef02d-719a-46f6-ac25-8851cde6da4e.png">
</p>
<p align = "center">
Fig.2 - Statistics summary for the Student Data Frame. 
</p>


More functions could be used here to display or store more values like:
-  The maximum value of a math or reading score using the ```max()``` function. 
- The number of data we have using the ```count()``` function. 

4. **Drill down into the data to analyze specific subsets.** <br />
In this section, we wanted to drill down in the data and target our analysis. <br />
Using ```loc``` and ```iloc``` we were able to display specific rows and columns. 

We have displayed:
- A summary statistic to grade 9 (See Fig.3)  
We can add here doing the same summary statistic to grade 10, 11 and 12. 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190836059-8123343d-93a5-4a4c-9569-8aad97e19a4a.png">
</p>
<p align = "center">
Fig.3 - Statistics summary for garde 9 students. 
</p>

- The row with the minimum reading score (See Fig.4)
We have found that the minimum value is for a student in " Dixon High School". Therefore, it is important to check all the reading scores in that school.

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190837948-2019e097-b817-4431-baab-9ab1beaa77b6.png">
</p>
<p align = "center">
Fig.4 - Row with the minimum reading score. 
</p>


- All reading scores from 10th graders at Dixon High School. <br /> 
By checking the reading scores for all students at Dixon High School, we didn't see any unusual trend. By using the ```mean()``` function I have found the average reading score in this school to be "67.781898" which is considered a good score. I have also checked the maximum value which was "99.9" <br /> 
We can certainly do the same to the math score column. I would suggest to:
	- Find the row with the minimum math score. 
	- Check in which school is the student with the lowest math value and in which grade.
	- Target this school by displaying all math score to that specific grade and school.

- The average reading score and math score for all students in grades 11 and 12 combined.

5. **Compare and contrast the data through grouping and aggregation functions.**<br /> 
In this section we have displayed the average of school budget in each school type. Using the 
```groupby()```and ```mean()``` functions we have found that the average school budget in Public schools is higher than in Charter schools.(See Fig.5)

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190836872-81a7e538-870e-42e0-91db-cb5dc9ee65e5.png">
</p>
<p align = "center">
Fig.5 - The average school budget in each school type. 
</p>

One more thing that could affect our analysis is the number of students in each school. Therefore, we have found the total number of students at each school, and sorted those numbers from largest to smallest by using ```groupby```, ```count```, and ```sort_values``` (See Fig.6)

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190836797-4b9022da-b10e-4f81-8e8e-e5efa77bc416.png">
</p>
<p align = "center">
Fig.6 - School names sorted by the number of students in each one.  
</p>

Lastly, we have found the average math score by grade for each school type. The results show no correlation between the type of school and the average of math score. Therefore, we cannot say that that the budget of school is affecting the math score. 
However, I would suggest doing the same analysis for reading score to check if we can find any trend. 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/190836712-559df41d-19f1-432e-afb2-bb12225e1302.png">
</p>
<p align = "center">
Fig.7 - The average math score by grade for each school type. 
</p>

## Summary
In this analysis we have followed a three-phase process: 

1. Collect the data. 
2. Prepare the data
3. Analyze the data

In order to help Maria analyzing the school district data and aggregate the data. Using this method, we were able to find and display a lot of useful information that could be used by both the direction and the parents, depending on what they want to find and what they want for the kids. 

### Challenges

While going through the code I have faced the following challenges: 
- In deliverable 4 of the challenge the question was to find that the mean reading score for all the students in Grades 11 and 12 is equal 63.25853039200117. However, this was the average value of the math score for all the students in Grades 11 and 12. While, for the reading score I found the average value to be equal to "74.900381"
- In the last question of derivable 5. It was challenging for me to change the number of digits from 6 after the comma to 1 (as shown in the challenge). I have tried ```pd.set_option()```
but it changed the number of digits in the whole code not only the table. I reset it by using 
```pd.reset_option('display.precision') ``` and found another way to do it using mapping. 




