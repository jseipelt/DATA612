# DATA612: Assignment 1

The purpose of this assignment is to become familiar with some of the basic functions of the pandas library.

I used data titled 'State Drug Utilization Data' found here for this purpose: 
https://raw.githubusercontent.com/frankData612/data_612/master/State_Drug_Utilization_Data_2010/State_Drug_Utilization_Data_2010.csv

I started by getting a glimpse of the ten first and last rows of the data set using the .head(10) and .tail(10) functions.

Next, I used the .columns function to show a list of every feature in the data set.

In order to see the type of data used for each feature, I used the dtypes function.

Another important piece of information to check for a new data set is the shape of the dataframe.
I used the shape function to determine the number of rows and columns in the dataframe which was (156220, 21)

Finally, I decided to determine the average number of prescriptions filled by quarter.
This was done using the groupby function where every prescription was grouped by their quarter.
The mean function was applied to each group to determine the average for each quarter.

Quarter
1    270.907023
2    335.029500
3    316.293268
4    338.122521
Name: Number of Prescriptions, dtype: float64
