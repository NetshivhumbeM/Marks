# Study hours and Marks Statstical Analysis


### Project Overview
![image](https://github.com/user-attachments/assets/65211cbe-7977-4bb2-bd92-19cffa38cb22)




The purpose of this project is to statistically analyze the relationship between Study hours and Marks obtained in order to determine whether students who studies for more than 6 hours show better results.

### Data source

Study hours and Marks Dataset - The primary dataset used for this analysis is "Scores_updated.csv" file, containing detailed information about the study hours and marks and was made accessible on kaggle.

### Tools Used
Python(Visual Studio) - Data Cleaning 
Python(Visual Studio) - Statistical analysis

### Data Cleaning and preparation
in the initial data preparation stage, we perfomed the following tasks:

Data loading and inspection
Checking for and Handling Missing Values
Data Cleaning and formatting

### Exploratory Data Analysis
The EDA process involved exploring the study hours and scores to answer key quetions such as:

1. Whether there is a  significant difference in the average marks betwwen students who study for more than 6 ours and those who study for lees than 6(Assuming that the variances of the two groups are the same)
2. Determinig whether the we made the right assumption by conducting an F test to check whether the variances are the same.If not conduct again a T test to question 1 above.
3. Determing whether the marks are normally distributed by using the shapiro wilks test
4. Visualization of the distribution of the marks.

### Data Analysis
Below is some of the interesting codes we used to be able to answer some of the quetions:

The following code is for quetion 2 in the EDA:

```python
from scipy.stats import levene
f_stat, p_value_f = levene(less_6,greater_6)
print("F test results")
print("The F-statistic is:",f_stat)
print("The p-value is:",p_value_f)

if p_value_f< alpha:
    print("We reject the null hypothesis and conclude that the variances are not equal")
    t_statsic,p_valuee = ttest_ind(less_6,greater_6,equal_var=False)
    print("T test results")
    print("The t-statistic is:",t_statsic)
    print("The p-value is:",p_valuee)
    if p_valuee< alpha:
       print("We reject the null hypothesis and conclude that there is a signincant difference in avareage marks between the two groups")
    else:
       print("We fail to reject the null hyphothesis and conclude that there is no enough information to show that there is a significant difference")

else:
    print("we fail to reject the null hypothesis and conclude that the variances are equal")
    t_statsic,p_valuee = ttest_ind(less_6,greater_6)
    print("T test results")
    print("The t-statistic is:",t_statsic)
    print("The p-value is:",p_valuee)
    if p_valuee< alpha:
        print("We reject the null hypothesis and conclude that there is a signincant difference in avareage marks between the two groups")
    else:
        print("We fail to reject the null hyphothesis and conclude that there is no enough information to show that there is a significant difference")
```

### Results or Findings
The analysis results are summarize as follows:
Using a significance level of 5%

1.Null hypothesis:There is no significant difference in the average marks betwwen students who study for more than 6 ours and those who study for lees than 6
  Alternative hypothesis:There is a significant difference in the average marks betwwen students who study for more than 6 ours and those who study for lees than 6
Assuming that the two groups have equal variances
T test results
The t-statistic is: -15.690257742884747
The p-value is: 5.360218764843392e-28
We reject the null hypothesis and conclude that there is a signincant difference in avareage marks between the two groups

2.F test procedure
Null hypothesis: Variance1 and Variance2 are equal
Alternative hypothesis Variance1 and Variance2 are not equal
F test results
The F-statistic is: 7.1911918683309555
The p-value is: 0.008654078347599115
We reject the null hypothesis and conclude that the variances are not equal
Variance are not equal
T test results
The t-statistic is: -16.72532597275376
The p-value is: 6.545422571902648e-30
We reject the null hypothesis and conclude that there is a signincant difference in avareage marks between the two groups

3.Null hypothesis:Data is normally distributed
  alt hypo:Data is not Normally distributed
  The Shapiro wilks test results
The Shapiro statstics is: 0.9519261116296355
The shapiro p value is: 0.0014601240979284173
We reject the null hypothesis.This means that the data significantly deviates from normality and therefor the data is not normally distributed

### Recommendations
Based on the data analysis i would recommend that the organization:

1Investigate the Effect Size:

Assess the magnitude of the difference between the two groups using effect size measures . This would help us understand the practical significance of the difference, beyond just statistical significance.

Analyze the Data Further:

Explore additional factors that might influence the results, such as study methods, prior knowledge, or other variables to gain a deeper understanding




