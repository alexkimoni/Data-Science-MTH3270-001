**Alex Kimoni  
homework-02**

**1.** Please answer the following questions
(a) Try the commands `pi`, `round(pi)`, `round(pi, digits = 4)`, and `trunc(pi)`, `ceiling(pi)`, `floor(pi)`. What are the results?
```R
> pi
[1] 3.141593
> round(pi)
[1] 3
> round(pi, digits = 4)
[1] 3.1416
> trunc(pi)
[1] 3
> ceiling(pi)
[1] 4
> floor(pi)
[1] 3
```
(b) Try the commands `sqrt(16)`, `16^0.5`. Are the results the same? Yes
```R
> sqrt(16)
[1] 4
> 16^0.5
[1] 4
```
(c) Write a command that computes `4^3`.
```R
> 4^3
[1] 64
```
(d) Try the commands `log10(1000)`, `log(1000)`. Then try the command `log2(64)`. What are the results? (Make sure you understand the different logarithmic functions.)
```R
> log10(1000)
[1] 3
> log(1000)
[1] 6.907755
> log2(64)
[1] 6
```
e) Look at the help page for log() by typing: `? log`. Read the first few lines. Does the text match your observations from the previous question?

<font color="green">Ans: Yes. `log10(1000) = y` and `10^y = 1000`.</font>

**2.** Use the following command to create a "character" vector representing a supermarket queue with Steve first in line:
```R
queue <- c("Steve", "Russell", "Alison", "Liam")
```
Write R commands involving square brackets [ ] and the assignment operator <- to update the supermarket queue successively as follows:
(a) Barry arrives (and gets in the last position of the line).
```R
> queue = c(queue, "Barry")
> queue     
[1] "Steve"   "Russell" "Alison"  "Liam"    "Barry" 
```
(b) Steve is served (so he leaves, and now Russell is first in line).
```R
> queue <- queue[-1]
> queue
[1] "Russell" "Alison"  "Liam"    "Barry"
```
(c) Pam arrives and talks her way to the front of the line (with just one item).
```R
> queue <- c("Pam", queue)
> queue
[1] "Pam"     "Russell" "Alison"  "Liam"    "Barry" 
```

(d) Barry gets impatient and leaves.
```R
> queue <- queue[-5]
> queue
[1] "Pam"     "Russell" "Alison"  "Liam"
```

**3.** Create the following objects.
```R
w <- 6
x <- 7
y <- 8
z <- 9
```
(a) Write a command that lists the objects in your Workspace.
```R
> objects()
[1] "w" "x" "y" "z"
```
(b) Write a command that removes x from the Workspace.
```R
> rm(x)
> objects()
[1] "w" "y" "z"
```
(c) Write a command that removes all the objects from your Workspace.
```R
> rm(list = ls())
> objects()
character(0)
```

**4.** R coerces TRUE and FALSE to 1 and 0 in arithmetic expressions, and so summing the elements of a "logical" vector counts the number of TRUEs. Consider the vector:
```R
x <- c(3, 2, 0, 1, 4, 5, 9, 0, 6, 7, 2, 8)
```
(a) What is the result of the following command?
```R
> x == 0
 [1] FALSE FALSE  TRUE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
```
(b) Write a command involving sum() and the "logical" vector x == 0 that counts the number of elements of x that are equal to 0.
```R
> sum(x == 0)
[1] 2
```
(c) Write a command that determines the proportion of elements of x that are equal to 0, assuming you don’t know the number of elements in x. Hint: The function length() may be useful.
```R
> sum(x == 0) / length(x == 0)
[1] 0.1666667
```

**5.**

(a) Write R commands that create three vectors below and report your R commands.
- `TrueAndMissing` containing values `TRUE` and `NA` (at least one of each in anyorder).
  ```R
  > TrueAndMissing <- c(TRUE,NA)
  > TrueAndMissing  
  ```
- `FalseAndMissing` containing values `FALSE` and `NA`.
  ```R
  > FalseAndMissing <- c(FALSE,NA)
  > FalseAndMissing  
  ```
- `Mixed` containing values `TRUE`, `FALSE` and `NA`.
  ```R
  > Mixed <- c(TRUE, FALSE, NA)
  > Mixed
  [1]  TRUE FALSE    NA
  ```
b) Apply the functions any( ) and all() to each of the vectors of part a and reportthe results.
```R
> any(TrueAndMissing)
[1] TRUE
> all(TrueAndMissing)
[1] NA
> any(FalseAndMissing)
[1] NA
> all(FalseAndMissing)
[1] FALSE
> any(Mixed)
[1] TRUE
> all(Mixed)
[1] FALSE
```

**Problem 2 (Easy):** Which of these kinds of names should be wrapped with quotation marks when used in R?
> file name

**Problem 4 (Easy):** A user has typed the following commands into the RStudio console:
```R
mylist <- list(x1 = "sally", x2 = 42, x3 = FALSE, x4 = 1:5)
```
What values do each of the following commands return?
```R
> is.list(mylist)
[1] TRUE
> names(mylist)
[1] "x1" "x2" "x3" "x4"
> length(mylist)
[1] 4
> mylist[[2]]
[1] 42
> mylist[["x1"]]
[1] "sally"
> mylist$x2
[1] 42
> length(mylist[["x4"]])
[1] 5
> class(mylist)
[1] "list"
> typeof(mylist)
[1] "list"
> class(mylist[[4]])
[1] "integer"
> typeof(mylist[[3]])
[1] "logical"
```
**Problem 9 (Easy):** A user has typed the following commands into the RStudio console.
```R
a <- c(10, 15)
b <- c(TRUE, FALSE)
c <- c("happy", "sad")
```
What do each of the following commands return? Describe the class of the object as well as its value.
```R
> data.frame(a, b, c)
   a     b     c
1 10  TRUE happy
2 15 FALSE   sad
```
**Class:** "data.frame"  
**Value:** a 2×3 data frame with columns:  
- a numeric: c(10, 15)  
- b logical: c(TRUE, FALSE)  
- c character: c("happy", "sad")  
In a data frame, each column can keep its own type (no coercion across columns).

```R
> cbind(a, b)
      a b
[1,] 10 1
[2,] 15 0
```
**Class:** "matrix" (specifically a numeric matrix)
**Value:** a 2×2 matrix with columns:
- column a: 10, 15
- column b: 1, 0
**Coercion:** logical b is coerced to numeric (TRUE → 1, FALSE → 0) because a matrix must have a single atomic type.

```R
> rbind(a, b)
  [,1] [,2]
a   10   15
b    1    0
```
**Class:** "matrix" (numeric matrix)  
**Value:** a 2×2 matrix with row names "a" and "b":
- first row (from a): 10 15
- second row (from b): 1 0  
**Coercion:** same as above (logical to numeric) to keep a single type.

```R
> cbind(a, b, c)
     a    b       c      
[1,] "10" "TRUE"  "happy"
[2,] "15" "FALSE" "sad"  
```
**Class:** "matrix" (character matrix)  
**Value:** a 2×3 character matrix containing "10", "TRUE", "happy", etc.  
**Coercion:** everything becomes character, because mixing character with other types in a matrix forces character coercion.
```R
> list(a, b, c)[[2]]
[1]  TRUE FALSE
```
**Class:** "logical"  
**Value:** c(TRUE, FALSE)  
Note: [[2]] extracts the second element itself (not a sublist).
