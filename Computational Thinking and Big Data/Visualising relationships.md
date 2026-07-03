Markdown
# Visualising Relationships with ggplot2

## 📌 Table of Contents
* [1. Introduction to Scatter Plots](#1-introduction-to-scatter-plots)
* [2. Adding Color Aesthetics](#2-adding-color-aesthetics)
* [3. Adding Layers (Trend Lines)](#3-adding-layers-trend-lines)

---

## <span style="color:#2A6F97">1. Introduction to Scatter Plots</span>

To visualize the relationship between two continuous variables, we use a basic scatter plot. In this example, we map engine displacement (`displ`) to the x-axis and city miles per gallon (`cty`) to the y-axis.

```r
ggplot(mpg) + 
  geom_point(mapping = aes(x = displ, y = cty))
Key Concept: ggplot() initializes the plot with the dataset, and geom_point() adds the layer of points (scatter plot) using the aesthetic mapping aes().

2. Adding Color Aesthetics
You can reveal deeper insights by mapping a third categorical variable to a visual property like color. Here, we color the points by the drivetrain type (drv): front-wheel drive (f), rear-wheel drive (r), or 4-wheel drive (4).

R
ggplot(mpg) + 
  geom_point(mapping = aes(x = displ, y = cty, colour = drv))
💡 Points are colored now by the type of drive:
f = Front-wheel drive

r = Rear-wheel drive

4 = 4-wheel drive

3. Adding Layers (Trend Lines)
To make patterns even clearer, you can overlay multiple geometric layers on the same plot. A common approach is to add a smooth trend line (geom_smooth()) on top of your scatter plot points (geom_point()).

Option A: Shared Global Mappings (Recommended)
By passing the primary aesthetics into ggplot() instead of individual geoms, both the points and the trend line will share the same x and y data automatically.

R
ggplot(data = mpg, mapping = aes(x = displ, y = cty)) + 
  geom_point(mapping = aes(colour = drv)) + 
  geom_smooth(method = "lm", se = FALSE, color = "black")








