# Chapter4 Tibbles & Data frames 
## 1. Data frames
a collection of columns  
- column name should be named    
- data stored can be many data types  
- each column should contain same number of data items   

### 1.1 Tibbles
- Never change the data type of the inputs  
- never change the name of your variables  
- never create row names  
- make printing easier: automatically pull up first 10 rows    

## 2. Create the data frame
- A`package` with data that can be accessed by loading that `package`
- An external file like a spreadsheet or CSV that can be imported into `R`
- Data that has been generated from scratch using `R` code

```
> data.frame(x = c(1, 2, 3) , y = c(1.5, 5.5, 7.5))
  x   y
1 1 1.5
2 2 5.5
3 3 7.5
```

## 3. Get information about the data frame
### 3.1 head

```
data('diamonds')
head(diamonds)
```
<img width="510" alt="image" src="https://user-images.githubusercontent.com/105503216/210127620-7daba298-f214-4109-abb3-60652ba1d3ff.png">

### 3.2 str: structure
columnnames, type of data  

```
str(diamonds)
```
<img width="590" alt="image" src="https://user-images.githubusercontent.com/105503216/210127646-086a9be2-5b55-442d-b349-9a77b66b8675.png">

```
glimpse(diamonds)
```

<img width="720" alt="image" src="https://user-images.githubusercontent.com/105503216/210127887-4053865b-537d-40ae-99a6-8390455f7ba0.png">

### 3.3 colnames

```
colnames(diamonds)
```
<img width="645" alt="image" src="https://user-images.githubusercontent.com/105503216/210127671-242d140e-0b52-401a-9e57-e6fd58fc729c.png">

## 4. make change to the data frame
### 4.1 mutate: increase a new column
```
library(dplyr)
mutate(diamonds, carat_2 = 100*carat)
```
<img width="591" alt="image" src="https://user-images.githubusercontent.com/105503216/210127743-ac9130fc-e64e-4162-ac74-4b4b3a676760.png">
