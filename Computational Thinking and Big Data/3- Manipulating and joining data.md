## <span style="color:#2A6F97"> Load library of flights to make data manipulating on it </span>
library(nycflights13)<br>
flights
## <span style="color:#2A6F97"> Using filter  </span>
The first verb that dplyr introduces is filter(). This lets us filter the subjects that we want, that is, filter rows. So first, pause for a second and decide what the subjects in the flights dataset are.

filter(flights, month == 1)   filter on month equal 1 filter (subject,condition).

<img width="699" height="311" alt="image" src="https://github.com/user-attachments/assets/0025e75b-5656-451e-92b4-c360b39daf42" />


filter(flights, month == 1, day == 1) filter on month and day

<img width="701" height="309" alt="image" src="https://github.com/user-attachments/assets/510c1ab6-95aa-4518-82f6-0f5735fbdfb4" />

## <span style="color:#2A6F97"> Aside - magrittr   use the magrittr or "pipe" symbol %>% </span>

flights %>% filter(month == 1, day == 1)

<img width="709" height="310" alt="image" src="https://github.com/user-attachments/assets/78cab468-cb0d-46b0-8dc6-5788d2b459eb" />

-------
## <span style="color:#2A6F97"> Select to select certain columns </span>

ncyflights13 dataset (or many “Big” datasets) is that it is too wide to fit onto the screen. In all the examples of filtering above we couldn’t even see all of the variables – there were always 12 columns which didn’t fit on the screen. It’d be nice if we could make our dataframe a bit narrower, so that we can fit the information we’re interested in (and nothing else) onto the screen. This is what select does – it’s essentially a filter, but for columns rather than rows.




flights %>% filter(carrier == "AA",month == 1, day == 1) %>% <b>select(flight,dep_time,arr_time)</b>

<img width="732" height="285" alt="image" src="https://github.com/user-attachments/assets/6223c998-f6c8-4e24-870b-61fa322c8311" />

select(flights, year:day)

<img width="395" height="263" alt="image" src="https://github.com/user-attachments/assets/806f8762-c8fc-481c-af03-1b6ee1be816f" />


## <span style="color:#2A6F97"> Making New Variables using mutate </span>
 add new columns? In the dataset flights, we have the departure delay dep_delay, which is the difference between the scheduled departure time (sched_dep_time) and the departure time (dep_time).
use mustate to add new variable to dataset
flights %>% mutate(delay = dep_time - sched_dep_time)
 add new column called delay to flights dataset
 
<img width="703" height="372" alt="image" src="https://github.com/user-attachments/assets/4291b986-52cb-4243-b97c-5bd6728d7cdc" />

then call flights will lead to show the new variable

<img width="706" height="386" alt="image" src="https://github.com/user-attachments/assets/94a7611e-54a6-4c17-a45c-e36973a7f6e5" />

## <span style="color:#2A6F97"> Grouping subjects based on criteria </span>
, I have a hypothesis about flight delays in New York City: I reckon they're worse in winter. Snowstorms, ice, wind... I suspect that all of these will make delays in the winter months of December, January, February, worse than in the summer months. To investigate this, you'll need to group flights by month, which you can do like this:
by_month <- group_by(flights,month)<br>
by_month

<img width="710" height="319" alt="image" src="https://github.com/user-attachments/assets/e4fc31b2-1395-420d-9415-9825c4259352" />

## <span style="color:#2A6F97"> Producing summary statistics for groups of subjects </span>

summarise(by_month, delay = mean(dep_delay, na.rm = TRUE))

<img width="582" height="377" alt="image" src="https://github.com/user-attachments/assets/aedcaa42-ba97-403f-81c0-1e71f8e1a8da" />

## <span style="color:#2A6F97"> Putting together multiple dataframes with common subjects </span>

<img width="718" height="55" alt="image" src="https://github.com/user-attachments/assets/9a503466-e640-480f-93d3-179aae89cef6" />



<img width="727" height="523" alt="image" src="https://github.com/user-attachments/assets/e34fd0d2-0557-4010-8a8f-a00c28271841" />





 








