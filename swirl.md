# Swirl() Notes
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

###New commands
head() will reveal column names and first 6 lines of data.frame

dim() will reveal the number of rows and columns of a data.frame

class() will reveal the class of an object. each column of a data.frame as its own class

lapply(OBJECT, FUNCTION) will take an object and apply the specified function to each of its component and return a list

sapply(OBJECT, FUNCTION) will take an object and apply passed function to each component and return a vector, matrix, or list

sum(DATAFRAMENAME#COLUMN_NAME) will apply the sum function to columns indicated in the data frame

NEW_VARIABLE_NAME <- DATAFRAME_NAME[,XX:YY] will subset the contents of the dataframe into a new dataframe with the XXth to the YYth columns. By having a blank before the column, this means all rows will be kept but only the XX:YY columns will be kept.




