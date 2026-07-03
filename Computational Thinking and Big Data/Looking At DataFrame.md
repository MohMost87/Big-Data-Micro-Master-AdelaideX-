## Introduction To R 
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

### Getting variables from a dataframe
## look at only part of a dataframe
mpg<b>$</b>model  <br>
<img width="675" height="339" alt="image" src="https://github.com/user-attachments/assets/aad3dab7-da26-4a66-a5cb-464bda44897d" />

## To Look at unique values 
unique(mpg$model)<br>
<img width="661" height="230" alt="image" src="https://github.com/user-attachments/assets/6cdf71ae-702b-412a-9866-5c5813ef817e" />

38 different types of cars in the dataset.<br>
## if we need particular entry in dataset
mpg[194,]<br>

<img width="677" height="101" alt="image" src="https://github.com/user-attachments/assets/1c55bf38-42ea-4c41-aa2a-a29e4c7efcbe" />

##  look at a range of rows and columns 
dataset[Row range,Column Range]<br>
mpg[194:198,1:4]<br>

<img width="344" height="151" alt="image" src="https://github.com/user-attachments/assets/e534b37b-8be3-42a4-960c-c89cd36351a0" />











