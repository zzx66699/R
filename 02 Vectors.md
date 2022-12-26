# Chapter2 Vector
## 1. Atomic vectors  
atomic vector can only contain elements of the same type  

<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/209518549-deb8adee-a0f6-4c82-8d53-54a367ef3315.png"><img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/209519050-42d890f3-58fe-4dac-98d2-fcd8816d7134.png">  

### 1.1 typeof()
determine what kind of data you are working with 

```
> typeof(c('a','b'))
[1] "character"
```

### 1.2 length()
determine how many elements it contains

```
> a <- c(12,234,5)
> length(a)
[1] 3
```

### 1.3 is.logical(), is.double(), is.integer(), is.character()
check if a vector is a specific type  

```
> x <- c(2L, 5L, 11L)
> is.integer(x)
[1] TRUE
```

### 1.4 To create a vector of integers
you must place an L directly after each number   

<img width="193" alt="image" src="https://user-images.githubusercontent.com/105503216/209519310-931530c6-dd95-4913-839f-d4bec680cb10.png">  

### 1.5 names()
name the elements of a vector

```
> x <- c(2L, 5L, 11L)
> names(x) <- c('a','b','c')
> x
 a  b  c 
 2  5 11 
```

## 2. list
Lists elements can be of any type—like dates, data frames, vectors, matrices, and more.   
Lists can even contain other lists.  

```
list("a", 1L, 1.5, TRUE)
```

### 2.1 str() 
how many elements it contains, and what types of elements a list contains  

```
> a <- list(12,'43sd',TRUE)
> str(a)
List of 3
 $ : num 12
 $ : chr "43sd"
 $ : logi TRUE
```

```
> a <- list(12,'43sd',TRUE)
> b <- list(2)
> c <- 4
> d <- list(a,b,c)
> str(d)
List of 3
 $ :List of 3
  ..$ : num 12
  ..$ : chr "43sd"
  ..$ : logi TRUE
 $ :List of 1
  ..$ : num 2
 $ : num 4
```

### 2.2 name the elements of a list when you first create it

```

> d <-list(hh = a, xx = b, ww = 3)
> d
$hh
$hh[[1]]
[1] 12

$hh[[2]]
[1] "43sd"

$hh[[3]]
[1] TRUE


$xx
$xx[[1]]
[1] 2


$ww
[1] 3
```

