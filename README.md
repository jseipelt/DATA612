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

---------------------------------
# DATA612: Assignment 2

This assignment introduced series along with using basic operations. 
These operations could be used to search or calculate values in the dataframe.

I imported a csv containing data on several scientists: https://raw.githubusercontent.com/chendaniely/\pandas_for_everyone/master/data/scientists.csv

The most recent date under the 'Died' column could be found by using the .max function from pandas.

I could determine the number of days differnce between the most recent date of death and the other scientists' dates of death by subtracting using datetime.
Numpys timedelta64 was then used to convert the difference in days to a diffrence in months.

I assigned the difference in months to a new column in the dataframe and finally created a new csv in order to save this new dataset.

---------------------------------
# DATA612: Assignment 3

The purpose of Assignment 3 is to become more familiarized with the seaborn library and its tools in plotting data.

I chose the penguin dataset from the seaborn library and decided to look at a single species, the Adelie.
The number of Adelie samples totaled to 152 penguins.

The first feature that I examined was the distribution of bill lengths.
The histogram that was plotted showed an imperfect normal distribution of bill lengths.
I chose a histogram here because they are best used when examaning a single variable.
Comparing bill length to body mass showed positive correlation between the two when examining a scatter plot with a regression line.
The scatter plot was a good choice here since I was working with two different variables.

I was curious to try the joint plot next, which groups close data points together into bins.
The joint plot also plots a histogram on each axes representing each variable.
The result looks elegant, but not the best choice in this situation due to the number of data points used.
I would try this plot again in the future when I have a dataset several times larger than the Adelie set I used.

---------------------------------
# DATA612: Assignment 4

This assignment introduces merges for dataframes and shows different options when confronted with missing values in your data.

I started by using the same penguin dataset as assignment 3. This was separated into two different dataframes by species.
Once separated, I demonstrated how to merge the two back together with the .merge function.
Listing each column for the left and right joins allowed them to sync back into a single column once again.

The number of missing values was calculated by first counting the number of non-missing values with the .count function.
Using .shape, the number of total rows was shown, and finally subtracting the former from the latter revealed the number of missing values for each column.
One option for missing values is to remove any row that contains them, but I decided to try using the forward fill function.
The previous value in the dataframe was filled into the missing value that comes after it, giving a reasonably consistent value with the rest of the dataframe.

---------------------------------
# DATA612: Assignment 5

This exercise covers how to convert to different datatypes and why it may be a good idea to do so.

After importing pandas, the State Drug Utilization Data csv was imported and I used the .dtypes function to look at the current data types of each feature.
With only two categories under Utilization Type, I decided to convert it from an object into a category using the .astype('category') function.
The NDC number is used as an identifier and not for any calculations, so this was converted from an int64 into a string using .astype('str').

---------------------------------
# DATA612: Assignment 6

This assignment focuses on regular expressions and writing basic functions and using the apply function with them.

The State Drug Utilization dataset contained product names that cut off part of a word after an open parenthesis. 
Using a regular expression, I specified a sub function that would replace '(' and any letters that come afterwards with an empty ''.
This cleans the Product Name column up and makes it easier to work with.

Next, a function was created to determine the mean, sum, mode, median and range of the 'Number of Prescriptions' column.
By defining the 'Number of Prescriptions' column, the operations were shortened considerably for each calculation.
Using the .apply function to print the statistics unfortunately printed once for every index in the column and will need improvement to properly print a single time.

---------------------------------
# DATA612: Assignment 7

This assignment taught how to use written functions and the groupby function to transform or filter the dataset.
A function was written as an example using the mpg dataset that shows several descriptive statistics that also had a separate row for groups of cylinders.
Using that function as a template, a new function was made to calculate the same descriptive statistics for the State_Drug_Utilization dataset.
I decided to do this while also grouping by State and using the apply function to show a separate row with the statistics for each state.


