---
title: "Vectors and Data Matrices"
date: "2024-01-17"
output:
  html_document: 
    theme: spacelab
    toc: true
    toc_float: true
    keep_md: true
  pdf_document:
    toc: yes
---

## Learning Goals
*At the end of this exercise, you will be able to:*    
1. Define data structures and provide examples of vectors and data matrices.  
2. Build a new vector and call elements within it.  
3. Combine a series of vectors into a data matrix.  
4. Name columns and rows in a data matrix.  
5. Select values and use summary functions in a data matrix.  

## Data Structures
In addition to classes of data, R also organizes data in different ways. These are called data structures and include vectors, lists, matrices, data frames, and factors. For now, we will focus on `vectors`.  

## Vectors
Vectors are a common way of organizing data in R.  We create vectors using the `c` command. The `c` stands for concatenate.  

A numeric vector.

```r
my_vector <- c(10, 20, 30)
```

A character vector. Characters always have quotes and may be referred to as "strings".

```r
days_of_the_week <- c("Monday", "Tuesday", "Wednesday", "Thrusday", "Friday", "Saturday", "Sunday")
```

A convenient trick for creating a vector is to generate a sequence of numbers.

```r
my_vector_sequence <- c(1:100)
my_vector_sequence
```

```
##   [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18
##  [19]  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35  36
##  [37]  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  53  54
##  [55]  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72
##  [73]  73  74  75  76  77  78  79  80  81  82  83  84  85  86  87  88  89  90
##  [91]  91  92  93  94  95  96  97  98  99 100
```

## Identifying vector elements
We can use `[]` to pull out elements in a vector. We just need to specify their position in the vector; i.e. day 3 is Wednesday.

```r
days_of_the_week[3]
```

```
## [1] "Wednesday"
```

## Practice
Work through these examples and make adjustments to the values to experiment.

1. Evaluate all numerics in `my_vector_sequence` to determine which has a value of 15.  

```r
my_vector_sequence[15]
```

```
## [1] 15
```

2. We can use operators such as <, >, ==, <==, etc. Show all values in `my_vector_sequence` that are less than 10.  How about less than or equal to 10?  

```r
my_vector_sequence[my_vector_sequence < 10]
```

```
## [1] 1 2 3 4 5 6 7 8 9
```

```r
my_vector_sequence[my_vector_sequence <= 10]
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10
```

```r
my_vector_sequence[my_vector_sequence == 10]
```

```
## [1] 10
```

3. If you use `[]` then you only get the values, not the logical evaluation of the entire vector. Experiment with this by adjusting the chunk below.    


## Data Matrices
Data matrices are a series of stacked vectors, similar to a data table. In the example below, we build a new data matrix using the matrix command.  

Box office earnings for Harry Potter movies (in millions!). Notice that these are separate vectors.  

```r
Philosophers_Stone <- c(317.5, 657.1)
Chamber_of_Secrets <- c(261.9, 616.9)
Prisoner_of_Azkaban <- c(249.5, 547.1)
Goblet_of_Fire <- c(290.0, 606.8)
Order_of_the_Phoenix <- c(292.0, 647.8)
Half_Blood_Prince <- c(301.9, 632.4)
Deathly_Hallows_1 <- c(295.9, 664.3)
Deathly_Hallows_2 <- c(381.0, 960.5)
```

Create a new object called `box_office`. Here we are using the `c` command to combine the vectors into one.

```r
box_office <- c(Philosophers_Stone, Chamber_of_Secrets, Prisoner_of_Azkaban, Goblet_of_Fire, Order_of_the_Phoenix, Half_Blood_Prince, Deathly_Hallows_1, Deathly_Hallows_2)
box_office
```

```
##  [1] 317.5 657.1 261.9 616.9 249.5 547.1 290.0 606.8 292.0 647.8 301.9 632.4
## [13] 295.9 664.3 381.0 960.5
```

Create `harry_potter_matrix` using the `matrix()` command. We need to tell R how to organize the `box_office` vector using the `nrow` and `byrow` commands.

```r
harry_potter_matrix <- matrix(box_office, nrow = 8, byrow = T) #Bry's Notes: nrow = number of rows, byrow = fill by row, T = true

harry_potter_matrix
```

```
##       [,1]  [,2]
## [1,] 317.5 657.1
## [2,] 261.9 616.9
## [3,] 249.5 547.1
## [4,] 290.0 606.8
## [5,] 292.0 647.8
## [6,] 301.9 632.4
## [7,] 295.9 664.3
## [8,] 381.0 960.5
```
## Name the rows and columns
Vectors `region` and `titles`, used for naming.

```r
region <- c("US", "non-US")
region
```

```
## [1] "US"     "non-US"
```


```r
titles <- c("Philosophers_Stone", "Chamber_of_Secrets", "Prisoner_of_Azkaban", "Goblet_of_Fire", "Order_of_the_Phoenix", "Half_Blood_Prince", "Deathly_Hallows_1", "Deathly_Hallows_2")
titles
```

```
## [1] "Philosophers_Stone"   "Chamber_of_Secrets"   "Prisoner_of_Azkaban" 
## [4] "Goblet_of_Fire"       "Order_of_the_Phoenix" "Half_Blood_Prince"   
## [7] "Deathly_Hallows_1"    "Deathly_Hallows_2"
```

Name the columns using `colnames()` with the vector region.

```r
colnames(harry_potter_matrix) <- region #Bry's Notes: colnames() is a function that allows you to name columns
```

Name the rows using `rownames()` with the vector titles.

```r
rownames(harry_potter_matrix) <- titles
```

Print `harry_potter_matrix`.

```r
harry_potter_matrix
```

```
##                         US non-US
## Philosophers_Stone   317.5  657.1
## Chamber_of_Secrets   261.9  616.9
## Prisoner_of_Azkaban  249.5  547.1
## Goblet_of_Fire       290.0  606.8
## Order_of_the_Phoenix 292.0  647.8
## Half_Blood_Prince    301.9  632.4
## Deathly_Hallows_1    295.9  664.3
## Deathly_Hallows_2    381.0  960.5
```

## Using a data matrix
Once you have a data matrix, you can perform lots of different analyses. For example, you can calculate the total earnings of each movie.

```r
global <- rowSums(harry_potter_matrix)
global
```

```
##   Philosophers_Stone   Chamber_of_Secrets  Prisoner_of_Azkaban 
##                974.6                878.8                796.6 
##       Goblet_of_Fire Order_of_the_Phoenix    Half_Blood_Prince 
##                896.8                939.8                934.3 
##    Deathly_Hallows_1    Deathly_Hallows_2 
##                960.2               1341.5
```

And even add a new column to reflect this calculation. `cbind()` adds columns.

```r
all_harry_potter_matrix <- cbind(harry_potter_matrix, global) #Bry's Notes: cbind() is a function that allows you to add columns. 
all_harry_potter_matrix
```

```
##                         US non-US global
## Philosophers_Stone   317.5  657.1  974.6
## Chamber_of_Secrets   261.9  616.9  878.8
## Prisoner_of_Azkaban  249.5  547.1  796.6
## Goblet_of_Fire       290.0  606.8  896.8
## Order_of_the_Phoenix 292.0  647.8  939.8
## Half_Blood_Prince    301.9  632.4  934.3
## Deathly_Hallows_1    295.9  664.3  960.2
## Deathly_Hallows_2    381.0  960.5 1341.5
```

## Practice
1. What are the total earnings for the US and non-US regions?  

```r
total_earn <- colSums(harry_potter_matrix)
total_earn
```

```
##     US non-US 
## 2389.7 5332.9
```

2. Add this information to the data matrix. Hint: you are adding a row, not a column.  

```r
all_harry_potter_matrix <- rbind(all_harry_potter_matrix, total_earn)
```

```
## Warning in rbind(all_harry_potter_matrix, total_earn): number of columns of
## result is not a multiple of vector length (arg 2)
```

```r
all_harry_potter_matrix
```

```
##                          US non-US global
## Philosophers_Stone    317.5  657.1  974.6
## Chamber_of_Secrets    261.9  616.9  878.8
## Prisoner_of_Azkaban   249.5  547.1  796.6
## Goblet_of_Fire        290.0  606.8  896.8
## Order_of_the_Phoenix  292.0  647.8  939.8
## Half_Blood_Prince     301.9  632.4  934.3
## Deathly_Hallows_1     295.9  664.3  960.2
## Deathly_Hallows_2     381.0  960.5 1341.5
## total_earn           2389.7 5332.9 2389.7
```


## A few Extras
The same methods of selecting elements in a vector apply to data matrices. We use `[]`. The following selects the value in the first column, second row.

```r
harry_potter_matrix[2,1]
```

```
## [1] 261.9
```

Adding a colon `:` selects the specified elements in a column.  

```r
harry_potter_matrix[1:4] #Bry's Notes: This selects the first four elements in the first column
```

```
## [1] 317.5 261.9 249.5 290.0
```

We can also select values in an entire row or column. This can be useful for calculations. Here we calculate the mean of the entire second column. 

```r
non_us_earnings <- all_harry_potter_matrix[ ,2]
mean(non_us_earnings)
```

```
## [1] 1185.089
```

## Wrap-up
Please review the learning goals and be sure to use the code here as a reference when completing the homework.  
-->[Home](https://jmledford3115.github.io/datascibiol/)
