# Chapter2 Vector
### 4.1.1 atomic vectors
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
