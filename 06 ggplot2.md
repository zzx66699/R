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
### 3.1 
