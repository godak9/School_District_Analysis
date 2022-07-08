# School_District_Analysis
## Overview 
### Initial Analysis
An analysis was performed in Jupyter Notebook on reading and math scores for schools in the Py City School District (found in the PyCitySchools.ipynb file). In the intiial analysis of the school district a high-level snapshot of the district's key metrics we created Pandas dataframes for the following metrics: the top five top and bottom performing schools based on overall passing ( math and reading school >= 70 ) rate, the average math score received by students in each grade level at each school, the average reading score received by students in each grade level at each school, school performance based on the budget per student, school performance based on the school size,  and school performance based on the type of school.
### Challenge Anlysis
Academic dishonesty was reported to the school board which revelaed alteration to Thomas High School ninth-grade math and readiing scores. For the challenge analysis we were tasked to replace the ninth grade math and reading scores with NaN's while keeping the rest of the data intact and repeat the school dustrict analysis and descirbe how the initial metrics were affected. 
## Results 
The Thomas High Shcool ninth-grade math and reading scores were replaced with NaN so they would not be counted in the distrcit summary. The NumPy Nan function was used to make the change. The following code was added to the original code to make this change (found in the PyCitySchools_Challenge.ipynb file):
```
import numpy as np
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th") , 'reading_score':'math_score'] = np.nan
```
A snapshot of the new student data dataframe: 
![Screen Shot 2022-07-07 at 9 24 19 PM](https://user-images.githubusercontent.com/104794100/177897969-0864dc24-cf30-4e6a-b51c-5c36f1150598.png)
### Effect on district summary 
A snapshot of the original district summary dataframe (found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 9 37 54 PM](https://user-images.githubusercontent.com/104794100/177899257-4abebd41-ff8b-40a5-ab0c-b59ee04153dc.png)
A snapsht of the new distrcit summary dataframe after Thomas High Shcool 9th grade scores were removed from the data(found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 9 28 25 PM](https://user-images.githubusercontent.com/104794100/177898618-389d21e9-d94a-4b3a-93d3-a021ea125584.png)
After replacing the Thomas High School ninth-grade with NaN there was a some change in the school district summary dataframe, but it only changed slightly. Because only 461 student scores were removed from data there was not a huge impact on the dataframe.  The average math school was lower by 0.1, the average reading score stayed the same, the percentage of passing math students was lower by 1.1%, the percentage of passing reading students was lower by 1.3%, and the percentage of overall passing students was lower by 0.9%.
### Effect on school summary
A snapshot of the original school summary dataframe showing results for Thomas High School(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 9 48 33 PM](https://user-images.githubusercontent.com/104794100/177900360-87552540-e137-4aaf-affc-f97639d8b7a3.png)
A snapsht of the new school summary dataframe showing result for Thomas High School after Thomas High Shcool 9th grade scores were removed from the data(found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 9 52 03 PM](https://user-images.githubusercontent.com/104794100/177900633-08f42e60-51f1-4c85-bdf1-9148fde557a1.png)
The impact of not including Thomas High School ninth grade students in the analysis was much more evident in this dataframe. Still, the average math and reading scores barely changed. The evident changes were in the percentage of passing math students, which was lower by a little over 26%, the percentage of passing reading students, which was lower by almost 28%, and the percentage of overall passing scores, which was lower by almost 25%.
### Effect of Thomas High School’s performance relative to the other schools
A snapshot of the original school summary dataframe showing results for all 15 schools(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 07 26 PM](https://user-images.githubusercontent.com/104794100/177902391-52464263-9fdd-4483-b996-948228182a66.png)
A snapshot of the new school summary dataframe showing results for all 15 schools after Thomas High Shcool 9th grade scores were removed from the data(found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 08 27 PM](https://user-images.githubusercontent.com/104794100/177902459-be0f5fd9-17e9-4f43-aff9-f290e20526da.png)
Orignally, Thomas High School was one of the top performing schools. After removing the ninth-grade student data, it was one of the bottom perfomring schools. 
How does replacing the ninth-grade scores affect the following:
### Effect on average math and reading scores by grade
A snapshot of the original math scores by grade dataframe(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 19 28 PM](https://user-images.githubusercontent.com/104794100/177903719-95b70ca2-3547-4015-993e-2e9c8181d008.png)
A snapshot of the original reading scores by grade dataframe(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 20 02 PM](https://user-images.githubusercontent.com/104794100/177903740-dc0f09c1-65cf-47cc-8a38-f81a8c984eb3.png)
A snapshot of the new math scores by grade dataframe (found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 15 01 PM](https://user-images.githubusercontent.com/104794100/177903321-0170e80d-4323-483b-98a1-81a10045cb95.png)
A snapshot of the new reading scores by grade dataframe (found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 15 29 PM](https://user-images.githubusercontent.com/104794100/177903551-de4e85fe-4791-4eee-90df-a02b363ed680.png)
The average math and reading scores for 10th, 11th, and 12h graders were not affected. The ninth grade average scores of 83.6 for math and 83.7 for reading were replaced with NaN.
### Effect on average math and reading scores by school spending
A snapshot of the original math and reading scores by school spending dataframe(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 25 40 PM](https://user-images.githubusercontent.com/104794100/177904573-a185ed39-ece3-4f1d-a9b9-0b0f445e496f.png)
A snapshot of the new math and reading scores by school spending dataframe (found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 26 08 PM](https://user-images.githubusercontent.com/104794100/177904643-c8560aa8-2859-4b5c-badb-a4850aef3bfa.png)
Thomas High School falls in the $631-$645 spending range, but there was not a huge effect when replacing the ninth grade data.
### Effect on average math and reading scores by school size
A snapshot of the original math and reading scores by school size dataframe(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 35 38 PM](https://user-images.githubusercontent.com/104794100/177905526-37146a97-78d5-40d3-9bce-466b08169e9e.png)
A snapshot of the new math and reading scores by school size dataframe (found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 34 56 PM](https://user-images.githubusercontent.com/104794100/177905475-60fb08c3-5df4-4282-a9fa-5b0279d95337.png)
Thomas High School is a medium size school, but there was not a huge effect when replacing the ninth grade data. The average math and reading scores stayed the same. The percentage of passing math students was lower by 0.02%, the percentage of passing reading students was lower by 0.06%, and the percentage of overall passing students was lower by 0.06%.
### Effect on average math and reading scores by school type
A snapshot of the original math and reading scores by school type dataframe(found in the PyCitySchools.ipynb file):
![Screen Shot 2022-07-07 at 10 36 13 PM](https://user-images.githubusercontent.com/104794100/177905607-d9407ea1-3d0f-45fd-a756-203d663c5f84.png)
A snapshot of the new math and reading scores by school size dataframe (found in the PyCitySchools_Challenge.ipynb file):
![Screen Shot 2022-07-07 at 10 33 48 PM](https://user-images.githubusercontent.com/104794100/177905370-a0f335bc-44c8-4d55-b975-9d18b956f327.png)
Thomas High School is a charter shcool, but there was not a hige effect when replacing the ninth grade data. 
## Summary: Four changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.
1. The passing math percentage of students for Thomas High School changed dramatically and was lower by a little over 26%.
2. The passing reading percetage of students for Thomas High School changed dramtically and was lowe by almost 28%.
3. The overall passing percentage of students for Thomas High School changed dramatically and was lower by almsot 25%.
4. Thomas High School went from being one of the top performing schools in the district to being one of the bottom performing schools in the district. 
