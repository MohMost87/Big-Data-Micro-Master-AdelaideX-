## <span style="color:#2A6F97"> Scaling data to normalise location and spread </span>
Where Gretzky Sits on the Z-Score ScaleWhen statisticians run the standardization formula on the points-per-game metrics of elite NHL players, Gretzky pulls away from the pack just like Bradman.Michael Jordan: $z = 3.4$Wayne Gretzky: $z \approx 5.8 \text{ to } 6.2$ (depending on the qualifying player baseline)Sir Donald Bradman: $z \approx 6.4$Assuming a normal distribution, a z-score hovering around $6.0$ puts Gretzky in a rarity tier of roughly 1 in 500 million.<br>

So, while Bradman still narrowly holds the crown as the ultimate statistical anomaly across all global sports ($z = 6.4$), Wayne Gretzky is the closest any athlete has ever come to reaching his level of absolute peer defiance.

<img width="314" height="472" alt="image" src="https://github.com/user-attachments/assets/55587a35-ee8a-4e94-b10d-ee15dcf6c16e" />


## <span style="color:#2A6F97"> Log transformations to adjust for skewness </span>
So, if our aim is to try and transform our data to a distribution which looks like a standard normal, or at least roughly symmetric, then -standardisation is a pretty limited tool. In fact, it doesn't do anything at all if our dataset is skewed. And unfortunately, a lot of real data can be pretty skewed.<br>

Here's an example. I do a lot of research on social media data - just today I was looking at a dataset of Twitter users, and trying to figure out how popular different users are. Here's a histogram of the follower counts of all the individuals in my dataset (please note this dataset isn't available in RStudio)
<img width="523" height="388" alt="image" src="https://github.com/user-attachments/assets/ed44d3e4-17fe-44a0-8955-d8cd0fd31348" />

summary(twitter)

<img width="644" height="618" alt="image" src="https://github.com/user-attachments/assets/520909a9-c51e-4d90-b645-3dfda58d8ee4" />


So how do we transform this to a more symmetric distribution? When confronted with skewed data a common trick is to use a log-transformation: , or in this case, , because we have zeros in the data and you can’t take the logarithm of zero. (You knew that, right?) If we do that here we get:
<img width="538" height="510" alt="image" src="https://github.com/user-attachments/assets/9db5814f-167a-46aa-8304-d02e8785fed1" />


## <span style="color:#2A6F97"> Automatic transformations </span>
This business of transforming data seems like hard work, because we need to know a little bit about our data - such as whether we expect it to be skewed or not - before we can decide on an appropriate transformation. And it becomes more complicated if we want to visualise the relationship between variables. It'd be nice if we had an automatic method we could throw at our data to find transformations automatically.<br>

For example, I have a box of dice at home that are of various sizes. I measured the side length of each die (in cm), as well as the volume (in mL) by putting the die in a jug of water and measuring the displacement (the things I do for this course!).
<img width="346" height="396" alt="image" src="https://github.com/user-attachments/assets/c47afad2-640f-42a0-838c-9c97326f6eee" />
<img width="532" height="446" alt="image" src="https://github.com/user-attachments/assets/6788ae95-adc7-4a73-a83a-f1c82cd684b4" />
<img width="798" height="529" alt="image" src="https://github.com/user-attachments/assets/03a3fbde-a750-40ae-8f5e-623a1aeb5d79" />
<img width="651" height="450" alt="image" src="https://github.com/user-attachments/assets/2c33ca7d-1747-465d-af64-8b12aa772ded" />

<img width="614" height="500" alt="image" src="https://github.com/user-attachments/assets/e75be85a-1290-428b-96af-fca4ab1b81b0" />

## <span style="color:#2A6F97"> Basic idea of PCA </span>
 What do you mean by dimension reduction? and <br>
 Why do I have to learn about PCA?

 











