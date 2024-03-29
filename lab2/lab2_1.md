---
title: "Objects, Classes & NAs"
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
1. Define an object in R.  
2. Use objects to perform calculations.  
3. Explain the difference between data classes in R.  
4. Use R to identify the class of specific data.  
5. Define NA in R.  
6. Determine whether or not data have NA values.  

## Objects
In order to access the potential of R we need to assign values or other types of data to `objects`. There is a specific format that I want you to follow, so please pay close attention.  

Assign a value to object 'x'. The '<-' symbol is read as 'gets'. In this case, x gets 42. Make sure that you are in the environment panel and you should see the value associated with 'x'. On a mac, you can push `option` and `-` to automatically generate the gets symbol. **On a PC, you can push `alt` and `=` to generate the gets symbol.**

```r
x <- 42
```

To print the object to the screen, just type x.  

```r
x
```

```
## [1] 42
```

Once an object has been created, you can do things with them.  

```r
treatment <- 36
control <- 38
```

Here we make a new object `my_experiment` that is the sum of the treatment and control. Notice that I use `_` and not spaces.  

```r
my_experiment <- sum(treatment, control)
my_experiment
```

```
## [1] 74
```

## Nomenclature
We need to be careful about nomenclature when we write code. R allows us to give almost any name we want to an object, but there are exceptions. For example, we don't want to give a name to an object that is the same as a function in R.  

```r
else <- 12
```

We get an error here because `else` is a function in R. You also don't want to give names that might get confused with functions; i.e. you can assign a value to 'mean' but this could become confusing because mean is used as a function.  

## Practice
1. Create three new objects, `venom_GT`, `chiron`, and `veyron`. These are the fastest cars in the world. Assign each car to its top speed. The venom_GT can go 270, chiron is 261, and veyron is 268.  

```r
venom_GT <- 270
chiron <- 261
veyron <- 268
```

2. Use arithmetic to calculate the mean top speed for the cars.

```r
(venom_GT + chiron + veyron) / 3
```

```
## [1] 266.3333
```

3. Use the function `mean()` to calculate the mean top speed for the cars.

```r
mean(venom_GT, chiron, veyron)
```

```
## [1] 270
```

```r
#Bry's Edit: use c() to combine the three objects into a vector
mean(c(venom_GT, chiron, veyron))
```

```
## [1] 266.3333
```

## Types of Data
There are five frequently used `classes` of data: 1. numeric, 2. integer, 3. character, 4. logical, 5. complex.

```r
my_numeric <- 42
my_integer <- 2L #adding an L automatically denotes an integer
my_character <- "universe"
my_logical <- FALSE
my_complex <- 2+4i
```

To find out what type of data you are working with, use the `class()` function. This is important because sometimes we will need to change the type of data to perform certain analyses.

```r
class(my_numeric)
```

```
## [1] "numeric"
```

You can use the `is()` and `as()` functions to clarify or specify a type of data.

```r
is.integer(my_numeric) #is my_numeric an integer?
```

```
## [1] FALSE
```


```r
my_integer <- 
  as.integer(my_numeric) #create a new object specified as an integer
```


```r
is.integer(my_integer) #is my_numeric an integer?
```

```
## [1] TRUE
```

## Missing Data
R has a special way to designate missing data, the NA. NA values in R have specific properties which are very useful if your data contains any missing values. Later this quarter we will have a session focused on dealing with NAs.  

NA values are used to designate missing data. `is.na` or `anyNA` are useful functions when dealing with NAs in data. 

```r
my_missing <- NA
```


```r
is.na(my_missing)
```

```
## [1] TRUE
```


```r
anyNA(my_missing)
```

```
## [1] TRUE
```

## Practice  
1. Let's create a vector that includes some missing data (we will discuss vectors more in part 2). For now, run the following code chunk.  

```r
new_vector <- c(7, 6.2, 5, 9, NA, 4, 9.8, 7, 3, 2)
```

2. As we did in homework 1, calculate the mean of `new_vector`.

```r
mean(new_vector)
```

```
## [1] NA
```

3. How do you interpret this result? What does this mean about NAs?  
**Bry's Notes:** The mean is NA because there is an NA value in the vector. The mean function does not know how to deal with NA values.

4. Recalculate the mean using the following code chunk. Why is the useful?  

```r
mean(new_vector, na.rm=T) #na.rm removes the NA values in the vector
```

```
## [1] 5.888889
```

## That's it! Let's take a break and then move on to part 2!

-->[Home](https://jmledford3115.github.io/datascibiol/)  
