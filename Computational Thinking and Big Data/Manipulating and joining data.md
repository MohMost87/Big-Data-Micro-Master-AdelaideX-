## <span style="color:#2A6F97"> Load library of flights to make data manipulating on it </span>
library(nycflights13)<br>
flights
## <span style="color:#2A6F97"> Using filter  </span>
The first verb that dplyr introduces is filter(). This lets us filter the subjects that we want, that is, filter rows. So first, pause for a second and decide what the subjects in the flights dataset are.

filter(flights, month == 1)   filter on month equal 1 filter (subject,condition).

<img width="699" height="311" alt="image" src="https://github.com/user-attachments/assets/0025e75b-5656-451e-92b4-c360b39daf42" />


