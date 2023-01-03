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

## 2. 

