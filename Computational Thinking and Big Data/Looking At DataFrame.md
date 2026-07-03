## Installing Tidyverse dataframe(Install.packages function)
install.packages("tidyverse")     
## Load the mpg dataframe contained in the tidyverse package:
library(tidyverse) <br>
mpg

## output will be 
<img width="657" height="278" alt="image" src="https://github.com/user-attachments/assets/691991cd-d23a-40bb-bfdc-0f13bb6b7faa" />

## create your own tibbles
mytibble <- tibble( <br>
  x = 1:4, <b>
  y = x^2, <br>
  z = y + 0.1<br>
)<br>
output<br>
<img width="292" height="256" alt="image" src="https://github.com/user-attachments/assets/73f445e4-b7ef-44d8-a475-5153b88d01b2" />

## create "tribbles" (a modern, user-friendly version of a data frame) layout row-by-row.
mytribble <- tribble(?<br>
  ~x, ~y, ~z,<br> 
  1, 4.2,"a",<br>
  3, 9.6,"b",<br>
  4,16.8,"c"  <br>
)<br>
mytribble<br>
<img width="204" height="133" alt="image" src="https://github.com/user-attachments/assets/53d730da-bf91-493d-a25d-5a2baf5f13ce" />

