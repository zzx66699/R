# Chapter1 Fundamental of R programming
## 1. Cloud Rstudio
https://posit.cloud/content/5167181  

## 2. Definition
### 2.1 Argument
Information that a function in R needs in order to run  

### 2.2 Variable / objects
A representation of a value in R that can be stored for use later during programming  

### 2.3 Function
A body of reusable code for performing specific tasks in R  

### 2.4 Operator
operator is a symbol that identifies the type of operation or calculation to be performed in a formula.  

#### 2.4.1 Arithmetic operators
<img width="810" alt="image" src="https://user-images.githubusercontent.com/105503216/210130836-bac9defa-0fd9-4303-8438-087e0b1fc01f.png">

#### 2.4.2 Relational operators
<img width="805" alt="image" src="https://user-images.githubusercontent.com/105503216/210130989-8a341b01-1bc6-4e93-b221-1a240ad51841.png">

#### 2.4.3 Logical operators
<img width="806" alt="image" src="https://user-images.githubusercontent.com/105503216/210131011-c3873074-01a7-4fd1-8d08-9f583ada067c.png">  

The main difference between element-wise logical operators (&, |) and logical operators (&&, ||) is the way they apply to operations with vectors.  
<img width="175" alt="image" src="https://user-images.githubusercontent.com/105503216/210131078-58a07e3a-076c-420f-ba0b-e5e4f62b6979.png">   
<img width="833" alt="image" src="https://user-images.githubusercontent.com/105503216/210131082-bdc5b931-1074-49ed-b57e-62fc5c290921.png">  
<img width="838" alt="image" src="https://user-images.githubusercontent.com/105503216/210131094-4a93b26e-65d3-4271-a750-801dcacc6966.png">


#### 2.4.4 Assignment operators
<img width="796" alt="image" src="https://user-images.githubusercontent.com/105503216/210212646-f9beaf77-d597-4407-9ac1-6e1b8f7ad20a.png">


## 3. Pipe
A tool in R for expressing a sequence of multiple operations, represented with "%>%"   
shortcut: cmd + shift + m  

``` R 
result <- ToothGrowth %>% 
  filter(dose==0.5) %>% 
  arrange(len)

View(result)
```

### 3.1 nested function
nested: code is contained within code that performs a broader function   
nested function: a function that is completely contained within another function  

```
arrange(filter(ToothGrowth, dose==5),len)
```


## 4. Data structure 
a data structure is a format for organizing and storing data  

### 4.1 Vector
A group pf data elements of the same type stored in a sequence in R  
You cannot have a vector that contains both logicals and numerics.  

### 4.2 list

### 4.3 Data frames
First, columns should be named.  
Second, data frames can include many different types of data, like numeric, logical, or character.  
Finally, elements in the same column should be of the same type.  

### 4.4 files
#### 4.4.1 Use the dir.create function to create a new folder, or directory, to hold your files. 

Place the name of the folder in the parentheses of the function. 

```
dir.create ("destination_folder")
```

#### 4.4.2 Use the file.create() function to create a blank file. 
Place the name and the type of the file in the parentheses of the function. Your file types will usually be something like .txt, .docx, or .csv.  

```
file.create (“new_text_file.txt”) 

file.create (“new_word_file.docx”) 

file.create (“new_csv_file.csv”) 
```

If the file is successfully created when you run the function, R will return a value of TRUE (if not, R will return FALSE). 

```
file.create (“new_csv_file.csv”)

[1] TRUE 
```

#### 4.4.3 Copying a file can be done using the file.copy() function. 
In the parentheses, add the name of the file to be copied.   
Then, type a comma, and add the name of the destination folder that you want to copy the file to.   

```
file.copy (“new_text_file.txt” , “destination_folder”)
```

#### 4.4.4 You can delete R files using the unlink() function. 
Enter the file’s name in the parentheses of the function.

```
unlink (“some_.file.csv”)
```

### 4.5 Matrices 
A matrix is a two-dimensional collection of data elements  
matrices can only contain a single data type. For example, you can’t have both logicals and numerics in a matrix.   

```
> matrix(c(3:8), nrow = 2)  
     [,1] [,2] [,3]
[1,]    3    5    7
[2,]    4    6    8

> matrix(c(3:8), ncol = 2)  
     [,1] [,2]
[1,]    3    6
[2,]    4    7
[3,]    5    8
```

## 6. create R script
<img width="259" alt="image" src="https://user-images.githubusercontent.com/105503216/209664571-0ea24115-ae48-4f1c-bea2-12885d4f72a1.png"><img width="293" alt="image" src="https://user-images.githubusercontent.com/105503216/209664647-84495c91-5dfc-4f20-a6ff-54893375351d.png">
<img width="280" alt="image" src="https://user-images.githubusercontent.com/105503216/209664683-46e3c746-b53f-499b-ac68-32acbf5e0150.png">

## 7. and & or
and: &  
or: | 

## 8. Tips for keeping codes readable
- Always put a space afer a comma(never before).   
<img width="484" alt="image" src="https://user-images.githubusercontent.com/105503216/209667244-d9f9e928-af76-476b-a468-c3a6dc24590e.png">   

- Do not place spaces around code in parentheses or square brackets (unless there’s a comma, in which case see above).   
<img width="479" alt="image" src="https://user-images.githubusercontent.com/105503216/209667402-79db7b0a-9092-431c-afa2-347a5a408124.png">  

- An opening curly brace should never go on its own line and should always be followed by a new line.   
- A closing curly brace should always go on its own line (unless it’s followed by an else statement). Always indent the code inside curly braces.  
<img width="481" alt="image" src="https://user-images.githubusercontent.com/105503216/209667722-ccef20a3-3d02-444e-9454-b3e8ba0d2df9.png">  

- When indenting your code, use two spaces. Do not use tabs or mix tabs and spaces.
- Always add the plus sign at the end of a line of code, never put it at the beginning of a line

## 9. Packages
### 9.1 Check the packages you install

```
installed.packages()
```

### 9.2 load installed package
package with check means the package is loaded  
<img width="362" alt="image" src="https://user-images.githubusercontent.com/105503216/210084305-832517ee-51de-448b-bc14-4900110f2aa9.png">  

```
library(askpass)
```

<img width="438" alt="image" src="https://user-images.githubusercontent.com/105503216/210084424-cb0b22dc-56e4-42e7-b296-c459a869aa6d.png">

### 9.3 list of packages
https://cran.r-project.org/web/views/

### 9.4 update

``` R
# update all packages  
update.packages()

# only update a certain package
install.packages('xx')
```

### 9.5 use installed data package

``` R
data('ToothGrowth')
View(ToothGrowth)
```
<img width="233" alt="image" src="https://user-images.githubusercontent.com/105503216/210123018-9979e64d-75c3-4056-8c21-2a1ebc143736.png">  

## 10. read the file  
- read_csv(): comma-separated values (.csv) files
- read_tsv(): tab-separated values files
- read_delim(): general delimited files
- read_fwf(): fixed-width files
- read_table(): tabular files where columns are separated by white-space
- read_log(): web log files
- read_excel(): excel

## 11. R markdown
A file format for making dynamic documents with R    
Markdown is a syntax for formatting plain text files  

```
installed.packages('rmarkdown')
```
<img width="448" alt="image" src="https://user-images.githubusercontent.com/105503216/211032892-5aeeba96-8fff-49fd-abd8-551d1fd4033c.png">
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/211032723-ef2c8dc1-0882-41e1-a473-75c5a125b82c.png">    

we can easily find each section by the content menu  
<img width="214" alt="image" src="https://user-images.githubusercontent.com/105503216/211179240-f20fa88b-3eca-4bc2-b3ce-24d0e2782a75.png">

### 11.1 YAML(header section)
a language for data that translates it so it's readable   
<img width="394" alt="image" src="https://user-images.githubusercontent.com/105503216/211178450-cf882d54-a323-42cd-aae7-f0f57e84d543.png">

### 11.2 Clickable link 
the link is formatted using angle brackets  
<img width="470" alt="image" src="https://user-images.githubusercontent.com/105503216/211178640-b13b7fa0-0e89-4de1-a810-04dccd84cd93.png">  

embed the link  
add the caption in square bracket and copy the link in parenthesis  
<img width="609" alt="image" src="https://user-images.githubusercontent.com/105503216/211178944-179a358d-ba3d-43cd-9303-eaa0bd4a9170.png">  
<img width="252" alt="image" src="https://user-images.githubusercontent.com/105503216/211178932-61a21def-89fc-4133-b684-6c25475d1378.png">


### 11.3 Bullet
we use asterisk   
<img width="716" alt="image" src="https://user-images.githubusercontent.com/105503216/211178818-14c608cb-a719-44b1-b78a-9584614b3742.png">

### 11.4 Image
- add exclamation point and a caption for the image in square bracket  
- copy the URL and insert it in parenthesis   
<img width="716" alt="image" src="https://user-images.githubusercontent.com/105503216/211179029-2f4bbbff-5f87-4b1c-9cee-edc4c6aef42e.png">

### 11.5 Code chunk
delimiter: a character that indicates the beginning or end of a data item  
shortcut: command + option + i   

change the code chunk options  
<img width="339" alt="image" src="https://user-images.githubusercontent.com/105503216/211179270-95a262ac-063c-4f87-92ca-bc182e240034.png">

### 11.6 Export the documentation  
Use 'knit' to get a HTML report    
<img width="228" alt="image" src="https://user-images.githubusercontent.com/105503216/211179422-a363f30a-46db-4e0d-8f91-9fa0b233a64c.png">
<img width="1113" alt="image" src="https://user-images.githubusercontent.com/105503216/211033534-5e3f56f7-4379-4df5-9b8c-9e8bd172530f.png">     

Use export to download them  
<img width="502" alt="image" src="https://user-images.githubusercontent.com/105503216/211179586-98428a1a-a033-4186-b941-e3fd7e19fd08.png">

#### 11.6.1 other format
In addition to the default HTML output (html_document), you can create other types of documents in R Markdown using the following output settings:   
<img width="770" alt="image" src="https://user-images.githubusercontent.com/105503216/211179516-26f3e906-31c3-453f-89a7-e9cc626afcea.png">  
<img width="757" alt="image" src="https://user-images.githubusercontent.com/105503216/211179535-a3a51fec-7b65-451e-bf46-82a487e0a1a5.png">

change the output in YAML   
<img width="211" alt="image" src="https://user-images.githubusercontent.com/105503216/211179506-ff0391d4-2821-475c-8c64-66d166034f2b.png">  
