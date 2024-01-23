---
title: "Lab 2 Homework"
author: "Bryshal Moore"
date: "2024-01-17"
output:
  html_document: 
    theme: spacelab
    keep_md: true
---

## Instructions
Answer the following questions and complete the exercises in RMarkdown. Please embed all of your code and push your final work to your repository. Your final lab report should be organized, clean, and run free from errors. Remember, you must remove the `#` for the included code chunks to run. Be sure to add your name to the author header above.  

Make sure to use the formatting conventions of RMarkdown to make your report neat and clean!  

1. What is a vector in R?  
A vector is a collection of data of the same type.It can be a collection of numbers, characters, or logical values.

2. What is a data matrix in R?  
A data matrix is a collection of vectors of the same length. It can be a collection of numbers, characters, or logical values.

3. Below are data collected by three scientists (Jill, Steve, Susan in order) measuring temperatures of eight hot springs. Run this code chunk to create the vectors.  

```r
spring_1 <- c(36.25, 35.40, 35.30)
spring_2 <- c(35.15, 35.35, 33.35)
spring_3 <- c(30.70, 29.65, 29.20)
spring_4 <- c(39.70, 40.05, 38.65)
spring_5 <- c(31.85, 31.40, 29.30)
spring_6 <- c(30.20, 30.65, 29.75)
spring_7 <- c(32.90, 32.50, 32.80)
spring_8 <- c(36.80, 36.45, 33.15)
```

4. Build a data matrix that has the springs as rows and the columns as scientists.  

```r
#Bry's Edit: use c() to combine the three scientis names into a vector
scientists <- c("Jill", "Steve", "Susan") #the order of the names is important
scientists
```

```
## [1] "Jill"  "Steve" "Susan"
```



```r
#Bry's Edit: use rbind() to combine the eight springs into a matrix. Use rbind() to combine the eight springs as rows into a matrix.
data_matrix <- rbind(spring_1, spring_2, spring_3, spring_4, spring_5, spring_6, spring_7, spring_8)
data_matrix
```

```
##           [,1]  [,2]  [,3]
## spring_1 36.25 35.40 35.30
## spring_2 35.15 35.35 33.35
## spring_3 30.70 29.65 29.20
## spring_4 39.70 40.05 38.65
## spring_5 31.85 31.40 29.30
## spring_6 30.20 30.65 29.75
## spring_7 32.90 32.50 32.80
## spring_8 36.80 36.45 33.15
```

```r
# Bry's Edit: use colnames() to name the columns of the data matrix.
colnames(data_matrix) <- scientists #this will add the names to the columns

data_matrix
```

```
##           Jill Steve Susan
## spring_1 36.25 35.40 35.30
## spring_2 35.15 35.35 33.35
## spring_3 30.70 29.65 29.20
## spring_4 39.70 40.05 38.65
## spring_5 31.85 31.40 29.30
## spring_6 30.20 30.65 29.75
## spring_7 32.90 32.50 32.80
## spring_8 36.80 36.45 33.15
```


5. The names of the springs are 1.Bluebell Spring, 2.Opal Spring, 3.Riverside Spring, 4.Too Hot Spring, 5.Mystery Spring, 6.Emerald Spring, 7.Black Spring, 8.Pearl Spring. Name the rows and columns in the data matrix. Start by making two new vectors with the names, then use `colnames()` and `rownames()` to name the columns and rows.

```r
# Bry's Edit: use c() to combine the eight spring names into a vector
spring_names <- c("Bluebell Spring", "Opal Spring", "Riverside Spring", "Too Hot Spring", "Mystery Spring", "Emerald Spring", "Black Spring", "Pearl Spring")

#Bry's Edit: use colnames() to name the columns of the data matrix.
row.names(data_matrix) <- spring_names #this will add the names to the rows

data_matrix
```

```
##                   Jill Steve Susan
## Bluebell Spring  36.25 35.40 35.30
## Opal Spring      35.15 35.35 33.35
## Riverside Spring 30.70 29.65 29.20
## Too Hot Spring   39.70 40.05 38.65
## Mystery Spring   31.85 31.40 29.30
## Emerald Spring   30.20 30.65 29.75
## Black Spring     32.90 32.50 32.80
## Pearl Spring     36.80 36.45 33.15
```


6. Calculate the mean temperature of all eight springs.

```r
# Bry's Edit: use mean() to calculate the mean temperature of all of the eight springs.
mean_Blue <- mean(data_matrix [1, 0:3])
mean_Opal <- mean(data_matrix [2, 0:3])
mean_Riverside <- mean(data_matrix [3, 0:3])
mean_Too <- mean(data_matrix [4, 0:3])
mean_Mystery <- mean(data_matrix [5, 0:3])
mean_Emerald <- mean(data_matrix [6, 0:3])
mean_Black <- mean(data_matrix [7, 0:3])
mean_Pearl <- mean(data_matrix [8, 0:3])

mean_springs <- c(mean_Blue, mean_Opal, mean_Riverside, mean_Too, mean_Mystery, mean_Emerald, mean_Black, mean_Pearl)
mean_springs
```

```
## [1] 35.65000 34.61667 29.85000 39.46667 30.85000 30.20000 32.73333 35.46667
```

7. Add this as a new column in the data matrix.  

```r
# Bry's Edit: use cbind() to add the mean_springs vector as a new column to the data matrix.
springs_data_matrix <- cbind(data_matrix, mean_springs)
springs_data_matrix
```

```
##                   Jill Steve Susan mean_springs
## Bluebell Spring  36.25 35.40 35.30     35.65000
## Opal Spring      35.15 35.35 33.35     34.61667
## Riverside Spring 30.70 29.65 29.20     29.85000
## Too Hot Spring   39.70 40.05 38.65     39.46667
## Mystery Spring   31.85 31.40 29.30     30.85000
## Emerald Spring   30.20 30.65 29.75     30.20000
## Black Spring     32.90 32.50 32.80     32.73333
## Pearl Spring     36.80 36.45 33.15     35.46667
```


8. Show Susan's value for Opal Spring only.

```r
# Bry's Edit: use the data matrix to find Susan's value for Opal Spring only.
(springs_data_matrix[2, 3])
```

```
## [1] 33.35
```

9. Calculate the mean for Jill's column only.  

```r
# Bry's Edit: use the data matrix to calculate the mean for Jill's column only.
mean_Jill <- mean(springs_data_matrix[0:8, 1])
mean_Jill
```

```
## [1] 34.19375
```

10. Use the data matrix to perform one calculation or operation of your interest.

```r
# Bry's Edit: use colSums() to calculate the sum of each column in the data matrix.
all_sums <- colSums(springs_data_matrix)

#Bry's Edit: use rbind() to add the sum of each column as a new row to the data matrix.
complete_data_matrix <- rbind(springs_data_matrix, all_sums)


complete_data_matrix
```

```
##                    Jill  Steve  Susan mean_springs
## Bluebell Spring   36.25  35.40  35.30     35.65000
## Opal Spring       35.15  35.35  33.35     34.61667
## Riverside Spring  30.70  29.65  29.20     29.85000
## Too Hot Spring    39.70  40.05  38.65     39.46667
## Mystery Spring    31.85  31.40  29.30     30.85000
## Emerald Spring    30.20  30.65  29.75     30.20000
## Black Spring      32.90  32.50  32.80     32.73333
## Pearl Spring      36.80  36.45  33.15     35.46667
## all_sums         273.55 271.45 261.50    268.83333
```


## Push your final code to GitHub!
Please be sure that you check the `keep md` file in the knit preferences.  
