# Chapter3 Dates and times
using the lubridate package  

```
install.packages("tidyverse") 
library(tidyverse)
library(lubridate)
```

## 1. Types
<img width="806" alt="image" src="https://user-images.githubusercontent.com/105503216/209523448-8a54d38f-78f9-43a1-af23-769579c7fb77.png">

## 2. today() & now()
```
> today()
[1] "2022-12-26"
> now()
[1] "2022-12-26 08:16:06 UTC"
```

## 3. Converting
### 3.1 Converting from strings 
#### 3.1.1 Date
First, identify the order in which the year, month, and day appear in your dates.   
Then, arrange the letters y, m, and d in the same order. That gives you the name of the lubridate function that will parse your date.  
R still returns the date in yyyy-mm-dd format  

```
> a <- '2022-1-2'
> ymd(a)
[1] "2022-01-02"

>  a <- '2022 1 2'
> ydm(a)
[1] "2022-02-01"

> a <- 'Jan 21 2'
> myd(a)
[1] "2021-01-02"
```

#### 3.1.2 Date-time
The ymd() function and its variations create dates.   
To create a date-time from a date, add an underscore and one or more of the letters h, m, and s (hours, minutes, seconds) to the name of the function  

```
> ymd_hms("2021-01-20 20:11:59")
[1] "2021-01-20 20:11:59 UTC"
> ymd_hm("2021-01-20 20:11")
[1] "2021-01-20 20:11:00 UTC"
```

### 3.2 Switching between existing date-time objects 
#### 3.2.1 as_date() 
to convert a date-time to a date 

```
> now()
[1] "2022-12-26 08:27:09 UTC"
> as_date(now())
[1] "2022-12-26"
```
