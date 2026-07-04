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








