# Chapter6 Tidyverse

a system of packages in R with a common design philosophy for data manipulation, exploration, and visualization  

``` 
library(tidyverse)
```

## 1. 8 core packages
ggplot2, tibble, tidyr, readr, purrr, dplyr, stringr, forcats  

## 2. dplyr
### 2.1 filter

``` R
library(dplyr)
filtered_data <- filter(ToothGrowth, dose==0.5)
View(filtered_data)
```
<img width="230" alt="image" src="https://user-images.githubusercontent.com/105503216/210123133-70d36ed7-21c6-4997-a63d-eda917acfdc8.png">

### 2.2 arrange 排序sort

``` R
# arrange(排序的data名, 按照排序的列）
arrange(filtered_data, len)
```

### 2.3 group_by & summarize

```
result <- ToothGrowth %>% 
  filter(dose==0.5) %>% 
  group_by(supp) %>% 
  summarize(mean_len = mean(len))

View(result)
```
<img width="228" alt="image" src="https://user-images.githubusercontent.com/105503216/210123567-10c68d8e-af04-4665-a879-237579017ec9.png">

```
