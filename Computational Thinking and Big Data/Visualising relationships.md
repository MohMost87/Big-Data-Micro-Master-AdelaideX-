

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

## Split each type of drive into its own plot using a facet_wrap
 ggplot(mpg, mapping = aes(x = displ, y = cty)) + <br>
  geom_point() + <br>
  geom_smooth() + <br>
  facet_wrap( ~ drv) <br>

  <img width="1076" height="569" alt="image" src="https://github.com/user-attachments/assets/32d86803-1c48-4f4d-9574-5a07775d2281" />


## Visualising common words and similarities between texts
Part 1 - Download the carroll_books.csv file and put it in your RStudio working directory (which you can find using the getwd() function). Load the two works for that author into R using as_tibble(read.csv(file = "carroll_books.csv", as.is = c("text"), encoding = "UTF-8"))).

Part 2 - Count the frequency of each word used, making sure to remove stop words. Hint: You may also like to produce some ggplots to help with your investigation.

Part 3 - Answer Questions 1-5.


# -------------------------------------------------------------------------
# Activity 4: Visualising common words and similarities between texts
# -------------------------------------------------------------------------

# Load required packages (install first if needed via install.packages())
library(tidyverse)<br>
library(tidytext)

# --- Part 1: Load the Dataset ---
##  Ensure "carroll_books.csv" is in your working directory (check with getwd())
carroll_data <- as_tibble(read.csv(<br>
  file = "carroll_books.csv", <br>
  as.is = c("text"), <br>
  encoding = "UTF-8"<br>
))

Quick inspection of the columns (typically expects 'text' and 'title' or 'gutenberg_id')
print("Initial data structure:")<br>
glimpse(carroll_data)


# --- Part 2: Tokenization, Stop Word Removal, and Word Counting ---

# 1. Break the text down into individual words (tokenization)
# 2. Filter out standard English stop words (like 'the', 'and', 'of')
# 3. Group by book and count frequencies
word_counts <- carroll_data %>%
  unnest_tokens(output = word, input = text) %>% 
  anti_join(stop_words, by = "word") %>%       
  filter(str_detect(word, "^[a-z]+$")) %>%     # Remove numbers, punctuation-only tokens
  count(gutenberg_id, word, sort = TRUE) 

print("Top frequent words after removing stop words:")
print(head(word_counts, 10))


# --- Data Visualization (ggplot2) ---

# Generate a bar chart comparing the top 10 most common words in both books

top_words_plot <- word_counts %>%
  group_by(gutenberg_id) %>%
  slice_max(n, n = 10) %>%
  ungroup() %>%
  mutate(word = reorder_within(word, n, gutenberg_id)) 

ggplot(top_words_plot, aes(x = n, y = word, fill = title)) +
  geom_col(show.legend = FALSE) +
  scale_y_reordered() +                        # Pairs with reorder_within
  facet_wrap(~title, scales = "free_y") +
  labs(
    title = "Top 10 Most Common Words in Lewis Carroll's Works",
    subtitle = "Stop words removed",
    x = "Word Count (Frequency)",
    y = NULL
  ) +
  theme_minimal()


  ## Top count 

  <img width="557" height="276" alt="image" src="https://github.com/user-attachments/assets/d9c5a392-cfef-413b-beb4-1331506fca7d" />


  <img width="1064" height="566" alt="image" src="https://github.com/user-attachments/assets/d11b582c-fd78-4e3b-a221-544de05d38c5" />




