#Week 3: Loop functions and debugging
##lapply(OBJECT, FUNCTION)
* lapply will attempt to coerce whatever object you send it into a list and return a list
* the returned list will contain the results of the object and the function you passed to lapply
* to pass additional arguments (and thus override defaults) with lapply, you will pass it those arguments after the function
* you can define a function and pass it in the paranthesis
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
*
