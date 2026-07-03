

## <span style="color:#2A6F97">1. Introduction to Scatter Plots</span>

To visualize the relationship between two continuous variables, we use a basic scatter plot. In this example, we map engine displacement (`displ`) to the x-axis and city miles per gallon (`cty`) to the y-axis.

ggplot(mpg) + <br>
  geom_point(mapping = aes(x = displ, y = cty))

  <img width="1078" height="574" alt="image" src="https://github.com/user-attachments/assets/5d5ba49d-77f6-4254-a91f-d5e954d84b10" />



## <span style="color:#2A6F97">2. Adding Color Aesthetics</span>

You can reveal deeper insights by mapping a third categorical variable to a visual property like color. Here, we color the points by the drivetrain type (drv): front-wheel drive (f), rear-wheel drive (r), or 4-wheel drive (4).

ggplot(mpg) + <br>
  geom_point(mapping = aes(x = displ, y = cty, colour = drv))

  <img width="1076" height="566" alt="image" src="https://github.com/user-attachments/assets/6774dff3-260a-4deb-956f-81102c36a4ff" />


## <span style="color:#2A6F97">3. Adding layers </span>

ggplot is built upon layers, making it an incredibly powerful tool for creating more complex visualisations. The layers let us build up the plot adding extra visualisations to discover the patterns in the data. For example, adding a trendline to our original scatter plot is simple:

 ggplot(mpg) + <br>
  geom_point(mapping = aes(x  = displ, y = cty)) + <br>
  geom_smooth(mapping = aes(x  = displ, y = cty)) <br>


  <img width="1074" height="567" alt="image" src="https://github.com/user-attachments/assets/609b6be2-3db0-45e0-b5f9-31215c689eb9" />

  ## Adding separate trendlines for each type of drive in our coloured scatterplot is similar:

   ggplot(mpg, mapping = aes(x = displ, y = cty, colour = drv)) + <br>
  geom_point() + <br>
  geom_smooth() <br>

<img width="1073" height="574" alt="image" src="https://github.com/user-attachments/assets/31bb3e4f-0224-45b0-a40e-b157b6e0d87b" />

  


