# Chapter6 ggplot2

## 1. Fundamental knowledge
- Aesthetic: a visual property of an object in you plot (position, color, shape, size)
- Geom: Geometric object used to represent your data (line chart, scatter plot, bar chart)
- Facets: Display smaller groups, or subsets of your data
- Label and annotation: Let you customize your plot (title, subtitle)
- Mapping: Match up a specific variable in your dataset with a specific aesthetic

### 1.1 Grammar
- begin a plot with the ggplot() function
- choose a geom by adding a geom() function
- map the variables you want to plot with aes() function

```
ggplot(penguins) + 
  geom_point(mapping = aes(x=flipper_length_mm, y=body_mass_g))
```

## 2. Aesthetic
### 2.1 Color

```
ggplot(penguins) + 
  geom_point(mapping = aes(x=flipper_length_mm, y=body_mass_g, color=species))
```
<img width="698" alt="image" src="https://user-images.githubusercontent.com/105503216/210580678-a5e250d3-7001-4a32-bab7-0e85316cd5b2.png">

### 2.2 Shape

```
ggplot(penguins) + 
  geom_point(mapping = aes(x=flipper_length_mm, y=body_mass_g, shape=species))
```
<img width="683" alt="image" src="https://user-images.githubusercontent.com/105503216/210580819-64111f3a-d6c9-4a7e-85fc-c31f60fb0510.png">

### 2.3 Transparent

```
ggplot(penguins) + 
  geom_point(mapping = aes(x=flipper_length_mm, y=body_mass_g, alpha=species))
```
<img width="488" alt="image" src="https://user-images.githubusercontent.com/105503216/210585119-b25e2d9f-0379-482f-9908-85329be14820.png">

### 2.4 Change overall plot without regard to specific variables
write code outside the aes function  
<img width="499" alt="image" src="https://user-images.githubusercontent.com/105503216/210586280-3a69b1af-9854-46fb-9bb0-1763beeeb5ad.png">

## 3. Geom
### 3.1 geom_smooth

```
ggplot(penguins) + 
  geom_point(mapping = aes(x=flipper_length_mm, y=body_mass_g), color='purple') +
  geom_smooth(mapping = aes(x=flipper_length_mm, y=body_mass_g))
```
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/210731582-185ad1ac-a26b-4051-8c81-a4b542810a24.png">

```
ggplot(penguins) + 
  geom_smooth(mapping = aes(x=flipper_length_mm, y=body_mass_g, linetype=species))
```
<img width="504" alt="image" src="https://user-images.githubusercontent.com/105503216/210731712-66751835-e6a3-4e0e-9b42-8368f5a5839f.png">

### 3.2 geom_jitter
creates a scatter plot and then adds a small amount of random noise to each point in the plot.   
it help to deal with over-lapping  

```
ggplot(penguins) + 
  geom_jitter(mapping = aes(x=flipper_length_mm, y=body_mass_g))
```
<img width="509" alt="image" src="https://user-images.githubusercontent.com/105503216/210732004-3e7c9cf2-5959-4f4c-b2d3-5429b2b633e0.png">

### 3.3 geom_bar
R automatically counts how many times each x-value appears in the data, and then shows the counts on the y-axis  

```
ggplot(penguins) + 
  geom_bar(mapping = aes(x=flipper_length_mm))
```
<img width="498" alt="image" src="https://user-images.githubusercontent.com/105503216/210735112-93d73482-1e42-4932-8f1e-d603dae2c0b4.png">

#### 3.3.1 color & fill
```
ggplot(penguins) + 
  geom_bar(mapping = aes(x=species, color=species))
```
<img width="499" alt="image" src="https://user-images.githubusercontent.com/105503216/210735557-3da1498b-5531-4f7d-94ba-63c5330495f7.png">

```
ggplot(penguins) + 
  geom_bar(mapping = aes(x=species, fill=species))
```
<img width="500" alt="image" src="https://user-images.githubusercontent.com/105503216/210736276-890950c5-036f-4b28-99b3-48dceedad41b.png">  


Map fill to a new variable, geom_bar will automatically display a stacked bar    
```
ggplot(penguins) + 
  geom_bar(mapping = aes(x=species, fill=sex))
```
<img width="502" alt="image" src="https://user-images.githubusercontent.com/105503216/210739326-6119c319-81e0-4cc7-8b01-8e7c802c34c5.png">

```
