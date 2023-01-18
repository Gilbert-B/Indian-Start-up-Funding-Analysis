# Indian-Start-up-Funding-Analysis
This repositiory seeks to document the process I undertook to analyze fundings received by Indian Start-ups from 2018 to 2021.

The project aims to draw insights on funding received by Indian startups and obtain a descriptive overview and a relationship pattern of funding and growth of newly launched startups.


# EXPLORATORY DATA ANALYSIS
Exploratory Data Analysis refers to the critical process of analysing data using visual techniques to discover patterns, to spot anomalies, to test hypothesis and to check assumptions. 

## Introduction

This article documents the process I undertook to analyse funding received by Indian Start-ups from 2018 to 2021. We will look at how Exploratory Data Analysis was performed on the data set using the Python programming language. External Python packages like Pandas, Numpy, Matplotlip etc was used to conduct univariate analysis, bivariate analysis, correlation analysis and handle duplicate and missing data.

The project aims to draw insights on funding received by Indian start-ups and obtain a descriptive overview and a relationship pattern of funding and growth of newly launched start-ups.
Jupyter Notebook was used in this analysis and all processes takes place in the Jupyter Notebook environment

## The Steps Involved

##  ***1.Installation***

The first step in our process is to install all the packages and libraries that will be used in our analysis. The following libraries and packages were installed 

•	Pandas

•	Numpy

•	Matplotlib

•	Seaborn

•	Forexpython

## ***2. Data Overview***
A. The necessary libraries used are imported (Pandas, NumPy & matplotlib, etc)

B. The Dataset is then loaded into the Jupyter Notebook for analysis. Our dataset is in a csv format so the pd.read_csv function is used to import the data and stored it in a DataFrame and give a label. The data set for all 2018,2019,2020 & 2021 are stored in df2018, df2019,df2020, and df2021 respectively.

## ***3. Gaining Insight on Our Data***

The following functions are used to gain more insight on the data that have been imported

a. df.shape() — To find out the total number of rows and columns in our data

The output of the code shows that the 2018 data set has 526 rows and 6 columns

b. df.head() — This function of pandas library returns the first five observations of the data set. It shows the ‘Head’ of the data set by displaying the first 5 rows of the data. Similarly “df.tail()” returns the last five observations of the data set i.e. the last 5 rows in the data set

c. df.info() prints out information about our data frame. It shows the various columns in the data set and their data type. As seen in the diagram below, our 2018 data set has 6 columns and all the datatype of the column is ‘object’. The df.info also provides us with how many of the rows in our column are not null i.e. have data in them. The df.shape() , df.head(), df.tail(), and df.info() methods were applied to all the data set used in our analysis to provide us with a holistic view of how our data set looks like.

After gaining a holistic view of our dataset, issues seen at first glance needed to be addressed and the purpose of this analysis had to be established. In some cases, this would mean that a specific problem was to be solved using the insights that will be derived from the analysis.

### Issues with The Data
After looking carefully at the data, the following issues were identified

· The 2018 Dataset had different and fewer columns

· The data sets have missing values

· Some values are in the wrong columns

· The datatypes of some of the columns need to be changed

· One column is unnamed

### How to Handle Issues
The issues identified would be handled by

· Analyse the 2018 data separately from the rest

· Replace missing data with either N/A or the mode of that column depending on the column data

· Move values in the wrong columns to their appropriate columns

· Change the datatype of columns to appropriate datatypes

· Rename columns

### Hypothesis
A null hypothesis was developed, and questions were asked to aid in the analysis process. At the end of the process, the null hypothesis would either be accepted or rejected based on the insights gleaned from the data.

Null Hypothesis — The sector of a start-up affects the amount of funding received.

Alternate Hypothesis — The sector of a start-up does not affect the amount of funding received

### Questions
The following questions were asked to assist in the data analysis process

Which company received the highest amount of funds?
Which company received the lowest amount of funds?
Which Industry received the highest amount of funding?
Which Industry received the lowest amount of funding?
Is there a correlation between company age and funds received?
Which location recorded the highest amount of funding received?
What is the average age of the start-ups?
What is the average amount of funding received each year?
How many companies were funded each year?

## ***4. Data Preparation & Cleaning***
At this stage, the data is prepared for analysis. This includes cleaning the data and dealing with null values. All issues that were identified in the preliminary stages are tackled before analysis can be conducted on the data to answer the questions.

In our issue-handling stage, we established that the 2018 data set would be cleaned and analyzed individually. This is the cleaning process I undertook.

1. All dashes (-) in the amount column were removed

2. Two new columns; Currency and Currency_Rate_Date is created. The currency symbols of the amounts are copied and put in the currency column. Amount values without currency symbols are assumed to be in dollars ($). The currency date is populated with 2018–12–31, which is the date we would use to convert all other currencies to dollars.

3. All currency symbols and commas in the amount column are removed and the datatype of that column is changed to a float. This is done to ensure that the Amount column contains only numeric values which can allow for numeric computations.

4. Another column; Amount_USD is created and populated with all amounts which have been converted to dollars to ensure uniformity. The new column; Amount_USD now contains the value of funding received in dollars for the year 2018. The column is formatted to 2 decimal places

As established, the 2019,2020, and 2021 data sets were combined and analyzed together.

After combining the datasets, the pandas attribute ‘df.unique()’ was used to look at the unique values in all the columns. Doing this enabled me to identify some values which were in the wrong columns.

Each column was cleaned individually using the following process

1. df.replace() function was used to replace foreign values in the columns with either 0 or N/A.

2. df.astype() was used to change the data type of the column to the preferred data type.

3. df.update() function was used to update multiple columns at once and df.fillna() was used to fill ‘nan’ values with the desired values.

4. After viewing the details of an unnamed column in the data set, I realized that it was a repetition of the Stage column. The column was then dropped using the df.drop() function.

5. A critical look at the unique values of the Stage column showed that some values were not supposed to be in that column. The pandas function df.str.contains() was used to extract rows that contained a specified string. Those values in the column were then removed. Vales that did not belong in the column were moved to their appropriate columns using df.loc and df.to_numpy()

6. df.rename() was used to rename some of the columns.

Our data is now ready to be analyzed and for insights to be drawn from it

## ***5. Answering the questions***
A combination of charts and code was used to answer the questions asked at the early stages of our analysis.

· Which company received the highest amount of funds?

The analysis conducted revealed that Alteria Capital received the highest amount of funds.
![Highest](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q1Highestfund.png)
![Lowest](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q2LowestFund.png)
![Industry](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q3IndustryHighest.png)
![Industrylowest](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q4IndustryLowest.png)
![Corellation](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q5Corellation.png)
![Heatup](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q5Heatmap.png)
![CompaniesFunded](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q9CompaniesFunded.png)
![CompaniesBarchat](https://github.com/Gilbert-B/Indian-Start-up-Funding-Analysis/blob/main/Screenshots%20of%20code/Q9CompaniesFundedBarChat.png)



