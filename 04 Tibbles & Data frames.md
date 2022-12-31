# Chapter4 Tibbles & Data frames 
## 1. Data frames
a collection of columns  
- column name should be named    
- data stored can be many data types  
- each column should contain same number of data items   

```
> data.frame(x = c(1, 2, 3) , y = c(1.5, 5.5, 7.5))
  x   y
1 1 1.5
2 2 5.5
3 3 7.5
```

## 2. Tibbles
- Never change the data type of the inputs  
- never change the name of your variables  
- never create row names  
- make printing easier: automatically pull up first 10 rows    
