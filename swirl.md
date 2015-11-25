# Swirl() R Programming Notes
## Lesson 8: Logic
### General notes
Some examples of Logical operators in R include:
* ==
* <=
* !=
* & and &&
* | and ||

for the && and || operators, they will only be applied to the first value of a vector 
& and | are applied to all values of the vector
### New commands
**isTrue()** If the argument passed to this function evaluates to TRUE, then it returns true. ALL other values (including numbers) will return false.

**indentical()** If the arguments passed are all identical, it evaluates to TRUE

**xor()** This function returns TRUE if *only one* of the arguments passed to it are true. It is the exclusive or.

**sample(10)** This gives us a random sampling of integers from 1 to 10 without replacement

**which()** The which function will return the index location of the items in the vector that meet the logical condition passed to the function

**and()** This function returns true if any elements of a vector meet the logical condition passed to it

**all()** This function returns true if ALL elements of the vector meet the logical condition passed to it

##Lesson 9: Functions
### General Notes
You can pass functions as arguments to other functions
You can set default values when writing functions 
You can pass a function as an argument without having defined the passed function. This is an anonymous function.
All arguments passed to a function after "..." MUST have a default value

When sending values in the parenthesis to a function, we call this passing an argument to a function

User-defined binary operators have the following syntax:

      %[whatever]% 
      
where [whatever] represents any valid variable name.

### New commands
**Sys.Date()**  returns the date

**mean()** returns the arithmetical average of all passed arguments

**args()** pass a function to this function to see its arguments and default values

**sd()** calculates the standard deviation

**paste()** will combine any number of strings into one string

##Lesson 10: Apply Functions

###General Notes

In general, if the result of sapply() is a list where every element is of length one, then sapply() returns a vector. If the result is a list where every element is a vector of the same length (> 1), sapply() returns a matrix. If sapply() can't figure things out, then it just returns a list, no different from what lapply() would give you.

lapply(OBJECT, function(dummy) dummy[2]) will return a list containing the second item from each element of the OBJECT list. Note that the function takes one argument, dummy, which is just a 'dummy variable' that takes on the value of each element of OBJECT, in turn. By defining our own function inside the call to lapply let's us do things in one line of code when R's built in functions isn't an option

###New commands
head() will reveal column names and first 6 lines of data.frame

dim() will reveal the number of rows and columns of a data.frame

class() will reveal the class of an object. each column of a data.frame as its own class

lapply(OBJECT, FUNCTION) will take an object and apply the specified function to each of its component and return a list

sapply(OBJECT, FUNCTION) will take an object and apply passed function to each component and return a vector, matrix, or list

sum(DATAFRAMENAME#COLUMN_NAME) will apply the sum function to columns indicated in the data frame

NEW_VARIABLE_NAME <- DATAFRAME_NAME[,XX:YY] will subset the contents of the dataframe into a new dataframe with the XXth to the YYth columns. By having a blank before the column, this means all rows will be kept but only the XX:YY columns will be kept.

unique() returns the unique values from an object (it eliminates all repeats)

## Lesson 11: Vapply and Tapply
### General notes

Vapply() can be thought of as safer as it will impose requirements on the returned information and if they are not met, you will not have undetected errors

### New commands

vapply(OBJECT, FUNCTION, DATATYPE(LENGTH)) will take an object, apply a function and return the specified datatype with the specified length. If the lengths vary from the object, you will receive an error.

table(OBJECT$COLUMN_NAME) will return  a table with a count of how many observations fall into each of the categorical values. Lets say we have 3 categories (A, B, C) this will return the number of observations that fall into each.

tapply(OBJECT$COLUMN_NAME, OBJECT2$COLUMN_NAME2, FUNCTION) will return the first column_name data organized by column_name2 applying the passed function

##Lesson 12: Looking at Data

###General notes

###New Commands
ls() lists all the variables in your current workspace

dim() will say the number of rows followed by the number of column

nrow() and ncol() will give the respective number of rows or columns of a passed object

object.size() will show the amount of memory an object is consuming in the memory

names() will show the names of the columns of a data.frame object

head(OBJECT, NUMBER) or tail() will show the first/last number of rows you specify. Default is 6

summary() will show summary statistical data for each of the columns

table(OBJECT$COLUMN_NAME) will show you each of the categorical values and the number of times they occur

str(OBJECT) will show a summary of information about a data.frame and its columns. You can also use it on a function

##Lesson 13: Simulation
###General Notes

Each probability distribution in R has:
* r function for random
* d function for density
* p function for probability
* q function for quantile

###New Commands

sample(x, size, replace = FALSE, prob = NULL) chooses a value to display from the vector x, and does this SIZE number of times. You can specify probabilities of outcomes with prob = c(PROBABILITY_VECTOR) that contains

LETTERS is a predefined object in R that contains each letter of the alphabet

rbinom(number of observations, size of trials, the probability of success)

rnorm(number of observations, mean = x, sd = X)
rpois()
replcate()

##Lesson 14: Dates and times

### General Notes

R stores date objects into unique object classes: either POSIXct or POSIXlt. POSIXct is the default

The base date for date storage is January 1, 1970

You can perform arithmetic and Boolean functions on time objects 

### New commands

Sys.Date() yields the date

unclass(OBJECT) will show you the raw value stored in an object versus the formatted output that an object class will output

as.Date("") will coerce a character string into a date object

Sys.time() will yield current system time

as.POSIXlt() will coerce an object into the POSIXlt object formatted

LISTOBJECT$valuename will return the value associated with a list

weekdays() months() quarters() all return the respective value associated with a particular date (i.e., Monday, November, Q4)

strptime() converts a character vector into POSIXlt. You must specify the format however with passed parameters

difftime() allows you to compare different time objects and calculate the delta between them and specify the units to return the value

##Lesson 15: Graphics

###General Notes

If there are only two columns in a data frame and you plot the data frame, it will automatically make the first column the X axis and the second column the Y unless you specify

http://www.ling.upenn.edu/~joseff/rstudy/week4.html provides a useful overview of many elements of base graphics

###New Commands

plot(DATAFRAME) will generate a scatterplot based on the data in the passed data frame.

boxplot(DATAFRAME) will generate a boxplot but the arguments for this function are a bit more complicated than plot. 

hist(vector) will generate a histogram based on the data passed

# Swirl() Data Analysis
##Lesson 1: Central Tendency
###General Notes
We installed the plotrix and openintro packages.

Remember: a population is the complete set of items to which a data set is refferring to

a subset of those items is a **sample**

The purpose of analyzing a sample is to draw conclusions about the population from which the sample was selected. This field is called **inferential statistics** 

Describing the sample is **descriptive statistics**

A good way to begin describing data is by looking at the "middle" or the central tendency of your sample: mean, median, mode

###New Commands

OBJECTNAME$variableName will extract a column from a dataframe

mean(object) or median(object) 

table(OBJECT or OBJECT$variableName) will give you a top row of all the values and a bottom row of their frequency count

##Lesson 2: Dispersion
###General Notes
The height of the box in the box and whisker plots are referred to as the interquartile range: the 25th and 75th percentiles respectively. These values are the medians of the bottom and top half respectively 

The whiskers represent the lower and upper 25th percentiles but may not include outlier values

Outliers may represent anomalies OR entry/collection errors

###New Commands
range(OBJECT) will give you the min and mix values for a vector

max(object) yields the maximum value

min(object) yields the minimum value

var(object) yields variance

sd(object) yields the standard deviation

##Lesson 3: Data Visualization
###General Notes
Think about skew has being the direction of the mean relative to the median
###New Commands
summary(OBJECT$COLUMN) will give summary statistics for a given numeric vector

# Swirl() Regression Models
## Lesson 1 Introduction
###General notes

Slides for this and other Data Science courses may be found at github https://github.com/DataScienceSpecialization/courses if you want to use them. 
They must be downloaded as a zip file and viewed locally. This lesson corresponds to Regression_Models/01_01_introduction

Sir Francis Galton did some of the pioneering work on "regression towards the mean" by looking at the heights of parents and their children

Because dot plots contain many points on top of each other, it is hard to see data concentration. We use jitter to account for this.

When calling summary on a regression line:

* VAR_NAME estimate is the slope of the line, or the co-efficient associated with the independent variable
* standard error represents the standard deviation for the slope of the line (in the VAR_NAME estimate)

Galton's work demonstrates the regression to the mean principle in that each centimeter of parent's height adds or substracts .65 cm from the expected value of children's height 

###New Commands

plot(YAXISOBJECT ~ XAXMISOBJECT, DATAFRAME_CONTAINING_OBJECTS) to get a dot plot the objects referenced

jitter(OBJECT, factor = X) will add noise to numbers to avoid dot stacking on a dot plot

lm(DEPENDENT_VAR ~ INDEPENDENT_VAR, DATAFRAME_CONTAINING_OBJECTS) will create a linear model, similar to plot 

abline(LINEARMODEL) will super-impose a line on top of a plot 
