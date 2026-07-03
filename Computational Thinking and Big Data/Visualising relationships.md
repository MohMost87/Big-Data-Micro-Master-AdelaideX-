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







