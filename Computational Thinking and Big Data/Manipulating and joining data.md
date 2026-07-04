## <span style="color:#2A6F97"> Load library of flights to make data manipulating on it </span>
library(nycflights13)<br>
flights
## <span style="color:#2A6F97"> Using filter  </span>
The first verb that dplyr introduces is filter(). This lets us filter the subjects that we want, that is, filter rows. So first, pause for a second and decide what the subjects in the flights dataset are.

filter(flights, month == 1)   filter on month equal 1 filter (subject,condition).

<img width="699" height="311" alt="image" src="https://github.com/user-attachments/assets/0025e75b-5656-451e-92b4-c360b39daf42" />


filter(flights, month == 1, day == 1) filter on month and day

<img width="701" height="309" alt="image" src="https://github.com/user-attachments/assets/510c1ab6-95aa-4518-82f6-0f5735fbdfb4" />

## <span style="color:#2A6F97"> Aside - magrittr  </span>

flights %>% filter(month == 1, day == 1)

<img width="709" height="310" alt="image" src="https://github.com/user-attachments/assets/78cab468-cb0d-46b0-8dc6-5788d2b459eb" />
