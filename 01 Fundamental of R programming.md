# Chapter1 Fundamental of R programming
## 1. Cloud Rstudio
https://posit.cloud/content/5167181  

## 2. Argument
Information that a function in R needs in order to run  

## 3. Variable / objects
A representation of a value in R that can be stored for use later during programming  

## 4. Data structure 
a data structure is a format for organizing and storing data  
You cannot have a vector that contains both logicals and numerics.  

### 4.1 Vector
A group pf data elements of the same type stored in a sequence in R  

#### 4.1.1 atomic vectors
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/209518549-deb8adee-a0f6-4c82-8d53-54a367ef3315.png"><img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/209519050-42d890f3-58fe-4dac-98d2-fcd8816d7134.png">  

#### typeof(): determine what kind of data you are working with 

```
> typeof(c('a','b'))
[1] "character"
```

#### length(): determine how many elements it contains

```
> a <- c(12,234,5)
> length(a)
[1] 3
```

#### is.logical(), is.double(), is.integer(), is.character()
check if a vector is a specific type  

```
> x <- c(2L, 5L, 11L)
> is.integer(x)
[1] TRUE
```

#### To create a vector of integers
you must place an L directly after each number   

<img width="193" alt="image" src="https://user-images.githubusercontent.com/105503216/209519310-931530c6-dd95-4913-839f-d4bec680cb10.png">  






#### 4.1.2 list

### 4.2 Data frames

## 05 Pipe
A tool in R for expressing a sequence of multiple operations, represented with "%>%"

``` R
ToothGrowth %>% filter(dose==0.5) %>% arrange(len)
```
