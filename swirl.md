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

