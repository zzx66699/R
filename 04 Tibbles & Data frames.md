# Chapter4 Tibbles & Data frames 
`tidyverse` is a system of packages in R with a common design philosophy for data manipulation, exploration, and visualization   

8 core packages of `tidyverse` are:    
ggplot2, tibble, tidyr, readr, purrr, dplyr, stringr, forcats  

we use `dplyr` a lot here

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

```
> install.packages('Tmisc')
> library(Tmisc)
> data(quartet)
> View(quartet)
```
<img width="221" alt="image" src="https://user-images.githubusercontent.com/105503216/210239509-f3fc4ffe-1162-4c86-8033-b39a644a94b6.png">  

- An external file like a spreadsheet or CSV that can be imported into `R`
- Data that has been generated from scratch using `R` code

```
> data.frame(x = c(1, 2, 3) , y = c(1.5, 5.5, 7.5))
  x   y
1 1 1.5
2 2 5.5
3 3 7.5
```

## 3. Clean functions: preview and clean data
### 3.1 head

```
data('diamonds')
head(diamonds)
```
<img width="510" alt="image" src="https://user-images.githubusercontent.com/105503216/210127620-7daba298-f214-4109-abb3-60652ba1d3ff.png">

### 3.2 str & glimpse & skim_without_chart
columnnames, type of data  

```
str(diamonds)
```
<img width="590" alt="image" src="https://user-images.githubusercontent.com/105503216/210127646-086a9be2-5b55-442d-b349-9a77b66b8675.png">

```
glimpse(diamonds)
```

<img width="720" alt="image" src="https://user-images.githubusercontent.com/105503216/210127887-4053865b-537d-40ae-99a6-8390455f7ba0.png">

```
install.packages(skimr)
library(skimr)
skim_without_charts(penguins)
```
<img width="733" alt="image" src="https://user-images.githubusercontent.com/105503216/210129225-132bc582-5036-4bff-aae7-0e14d7377469.png">


### 3.3 colnames

```
colnames(diamonds)
```
<img width="645" alt="image" src="https://user-images.githubusercontent.com/105503216/210127671-242d140e-0b52-401a-9e57-e6fd58fc729c.png">

### 3.4 clean_names
This ensures that there's only characters, numbers, and underscores in the names 

```
library(janitor)
clean_names(penguins)
```

### 3.5 rename & rename_with
change island to island_new (this will return a new dataset, not change the original one)

```
penguins %>% 
  rename(island_new = island)
```

<img width="687" alt="image" src="https://user-images.githubusercontent.com/105503216/210129828-b90237cb-6707-4a43-9916-f0e0e53e7adf.png">

#### 3.5.1 change all column name to upper/lower

```
penguins %>% 
  rename_with(toupper)
```
<img width="685" alt="image" src="https://user-images.githubusercontent.com/105503216/210130339-7bc4f3d6-e612-4d56-aca9-59319e32ee61.png">

## 4. Organize functions: sort, filter, and summarize data 
### 4.1 select

```
select(penguins, species)
```

<img width="207" alt="image" src="https://user-images.githubusercontent.com/105503216/210129757-ecd91bfb-a097-4a84-818f-d2b2b1896274.png">

```
penguins %>% 
  select(-species)
```

<img width="633" alt="image" src="https://user-images.githubusercontent.com/105503216/210129774-f600c4d6-4f01-4d36-bd5e-e9b57a9b4b88.png">

### 4.2 filter

``` R
library(dplyr)
filtered_data <- filter(ToothGrowth, dose==0.5)
View(filtered_data)
```
<img width="230" alt="image" src="https://user-images.githubusercontent.com/105503216/210123133-70d36ed7-21c6-4997-a63d-eda917acfdc8.png">


### 4.4 arrange: sort the dataset by xx column

```
# arrange(排序的data名, 按照排序的列）

penguins %>% 
  arrange(bill_length_mm)
```
<img width="671" alt="image" src="https://user-images.githubusercontent.com/105503216/210213040-8fcc7309-b3d9-4112-b5ed-b262e24e114e.png">  

descending order

```
penguins2 <- arrange(penguins, -bill_length_mm)
View(penguins)
```
<img width="669" alt="image" src="https://user-images.githubusercontent.com/105503216/210213254-51c20d14-f7ee-4f2b-994b-dd4b5d6d2e49.png">

### 4.5 group_by & summarize
#### 4.5.1 summarize without groupby
Make a column called 'total_canceled' to represent the total number of canceled bookings

```
> df <- hotel_bookings %>% 
+ summarize(total_canceled = sum(is_canceled))
> df
```

<img width="139" alt="image" src="https://user-images.githubusercontent.com/105503216/210217083-679d3dd4-3246-4bc1-822f-c680485b88cd.png">

#### 4.5.2 mean/ max/ sd/ cor

```
result <- ToothGrowth %>% 
  filter(dose==0.5) %>% 
  group_by(supp) %>% 
  summarize(mean_len = mean(len))

View(result)
```

<img width="228" alt="image" src="https://user-images.githubusercontent.com/105503216/210123567-10c68d8e-af04-4665-a879-237579017ec9.png">  

```
> quartet %>% 
+ group_by(set) %>% 
+ summarize(mean(x), sd(x), mean(y), sd(y), cor(x,y))
```
<img width="427" alt="image" src="https://user-images.githubusercontent.com/105503216/210240109-a6e88720-afdd-424d-acf1-975120377aaf.png">


#### 4.5.3 groupby multiple columns or calculate several results

```
penguins %>% 
  group_by(island, species) %>% 
  drop_na() %>% 
  summarize(max_bill_length = max(bill_length_mm), mean_bill_length = mean(bill_length_mm))
```
<img width="408" alt="image" src="https://user-images.githubusercontent.com/105503216/210214095-61b94438-c83e-4566-a36e-df8d96ad59b4.png">




## 5. Transfrom functions: separate and combine data, as well as create new variables
### 5.1 mutate: increase a new column 
```
library(dplyr)
diamonds1 <- mutate(diamonds, carat_2 = 100*carat)
View(diamonds1)
```
<img width="591" alt="image" src="https://user-images.githubusercontent.com/105503216/210127743-ac9130fc-e64e-4162-ac74-4b4b3a676760.png">

### 5.2 separate 

```
# separate(dataset, column, into = c('xx', 'xx'), sep = 按照xx分)

separate(example_df, hotel, into = c('word1','word2'), sep = ' ') 
```

<img width="721" alt="image" src="https://user-images.githubusercontent.com/105503216/210236310-e0604990-af87-4c2b-91eb-762e3ae1f89a.png">

### 5.3 unite
```
# unite(dataset, 合并成的那一列名字, c(combine的列xx, combine的列xx), sep = 'xx')

example_df <- hotel_bookings %>%
  select(arrival_date_year, arrival_date_month) %>% 
  unite(arrival_month_year, c("arrival_date_month", "arrival_date_year"), sep = " ")
example_df
```
<img width="156" alt="image" src="https://user-images.githubusercontent.com/105503216/210215979-d7569424-cf75-4470-b228-986db5efa8a6.png">



## 6. Wide data & long data
<img width="782" alt="image" src="https://user-images.githubusercontent.com/105503216/210237437-ff5d1c57-0c8b-4977-b553-70ff15320a9f.png">  
<img width="788" alt="image" src="https://user-images.githubusercontent.com/105503216/210237555-53b1318c-c32d-4a2d-8569-ae608b908386.png">  
pivot_wider() & pivot_longer()  



