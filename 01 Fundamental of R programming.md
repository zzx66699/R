# Chapter1 Fundamental of R programming
## 1. Cloud Rstudio
https://posit.cloud/content/5167181  

## 2. Argument
Information that a function in R needs in order to run  

## 3. Variable / objects
A representation of a value in R that can be stored for use later during programming  

## 4. Data structure 
a data structure is a format for organizing and storing data  

### 4.1 Vector
A group pf data elements of the same type stored in a sequence in R  
You cannot have a vector that contains both logicals and numerics.  

### 4.2 list

### 4.3 Data frames

### 4.4 files

## 05 Pipe
A tool in R for expressing a sequence of multiple operations, represented with "%>%"

``` R
ToothGrowth %>% filter(dose==0.5) %>% arrange(len)
```
