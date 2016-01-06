#Week 3: Loop functions and debugging
##lapply(OBJECT, FUNCTION)
* lapply will attempt to coerce whatever object you send it into a list and return a list
* the returned list will contain the results of the object and the function you passed to lapply
* to pass additional arguments (and thus override defaults) with lapply, you will pass it those arguments after the function
* you can define a function and pass it in the paranthesis
* 
##sapply(OBJECT, FUNCTION)
* essentially the same thing as lapply, except it does not always return a list: it will try to return a simple data type
* if it can't figure it out, it will just return a list


##apply function: apply(ARRAY, MARGIN, FUNCTION)
* you can use apply on arrays or matrices: which are vectors that have dimensional attributes
* apply is good because you do it one line
* ARRAY means the data object itself
* MARGIN refers to which dimension will be kept: 1 = vertical (keep # of rows the same) 2 = horizontal (keep # of columns same) 
* for sums and means, there are specialized functions: rowSums, rowMeans, colSums, colMeans
* for an array (3-D matrix), use c(1,2) for the margin argument where 1 and 2 indicate the dimensions you want to keep

##mapply function: mapply(FUNCTION, OBJECT, OBJECT...)
* this will create a loop that runs the function and passes it each object in the vector in the order that the function takes arguments
* so for example, mapply(rnorm, 1:5, 6:10, 1) will do the following:
* rnorm(1,6,1)
* rnorm(2,7,1)
* rnorm(3,8,1)
* rnorm(4,9,1)
* rnorm(5,10,1)

##tapply is used to apply a function over a subset of a vector
* tapply needs X which is a vector
* it needs an index which is a a categorical vector of the same length as the original vector
* a function that will be applied to the subset
* It will then apply the function on each block of the vector that has the same value in the factor index

##split will break a vector down into groups determined by the specified factors or list of factors
* splt(OBJECTyouWANTtoSPLIT, FACTORforSPLITTING)
* you can also split on multiple levels
* you can use the interaction function to look at factor combinations OR
* you can pass a list like this: split(OBJECT, list(factor1, factor2))
* specify drop =TRUE then it will clear out the empty factor combinations

##Debugging: when something is wrong
There are 4 levels of indicators that there is an issue
* message: not inteherently bad but a message function was tipped off. execution continues
* warning: something is wrong but not fatal, execution continues
* error: a fatal problem has occurred and execution stops. A stop function was tripped off
* condiition: a generic concept for indicating that something unexpected occurred; programmers can create their own conditions

When something has gone wrong with a function:
* what was your input? What was the ACTUAL input? How did you call it?
* What did you expect?
* What did you get as output?
* How was this different from what you were expecting
* Were your expectations corret in the first place?
* Can you reproduce the problem predictably? 

traceback
* will tell you where the error occured within the function stack
* Very handy to print out traceback when getting help
* will only give you the most recent error
debug
* you can debug any function
* first thing it does is to print the entire code for the function

#Week 4: Simulation and Profiling
##str function
Compactly displays internal structure of an R object
* Alternative to summary
* Well suited for displaying large lists or nested lists
* One line of output for each object

str(FUNCTION) will display one line on how to use the function

str(OBJECT) will display a one line summary of data type and the first couple values in the vector

str(DATAFRAME) will display number of observations, the names of the columns and the first few values

##Simulation: Random Number Generation
RNORM, DNORM, PNORM, RPOIS are native existing number distribution
* Each has a D (density) R (random number generation) P (cumulative distribution) and Q (quantile) function
* The random number seed must be set for reproducibility: set.seed(1) will set the seed to 1
* 
