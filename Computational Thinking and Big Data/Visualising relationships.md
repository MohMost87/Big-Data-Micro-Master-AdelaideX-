## Visualising relationships

## How to produce a scatter plot

ggplot(mpg) + <br>
geom_point(mapping = aes(x  = displ, y = cty)) <br>

<img width="1089" height="606" alt="image" src="https://github.com/user-attachments/assets/6dec965d-6ac4-46ec-ba00-5b841726a512" />



## Visualizations using ggplot library

ggplot(mpg) + geom_point(mapping = aes(x = displ, y = cty, colour = drv))
// this code using ggplot then point to create scatter plot also in aes   should put x axis y axis and colour if need to define some data point by color which use to plot the typr of colors of car.

<img width="1093" height="611" alt="image" src="https://github.com/user-attachments/assets/b1857363-4cb8-4496-a060-e057a71522e7" />






