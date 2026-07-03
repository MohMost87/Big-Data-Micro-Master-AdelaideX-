

## <span style="color:#2A6F97">1. Introduction to Scatter Plots</span>

To visualize the relationship between two continuous variables, we use a basic scatter plot. In this example, we map engine displacement (`displ`) to the x-axis and city miles per gallon (`cty`) to the y-axis.

ggplot(mpg) + <br>
  geom_point(mapping = aes(x = displ, y = cty))

  <img width="1078" height="574" alt="image" src="https://github.com/user-attachments/assets/5d5ba49d-77f6-4254-a91f-d5e954d84b10" />



## <span style="color:#2A6F97">2. Adding Color Aesthetics</span>

You can reveal deeper insights by mapping a third categorical variable to a visual property like color. Here, we color the points by the drivetrain type (drv): front-wheel drive (f), rear-wheel drive (r), or 4-wheel drive (4).
