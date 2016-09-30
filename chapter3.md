---
title       : Descriptive Statistics 
description : What are descriptive statistics and why is it important? 

--- type:NormalExercise lang:r xp:100 skills:1 key:fee7a4f081
## What are Descriptive Statistics ?

A good definition of descriptive statistics are brief summary statistics 
that summarize a given dataset. In general, when we have a new dataset, 
we know nothing about it and this is the best point to start. We want to 
calcuate some descriptive statistics!

There are five general functions in R to calculate mean, sd, min, max and median.
And this is pretty intuitive. And X will be the dataset name. 

mean(x)
sd(x)
min(x)
max(x)
median(x)

A dataset with a selection of movies, `film`, is available in the workspace.

*** =instructions
- Check out the structure of `film'. 
- Five common descriptive statistics that we like to look at:mean, sd, min, max, median,
- We will calculate all five of these descriptive stats in R


*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
film <- read.csv("http://s3.amazonaws.com/data415/film.csv", header = TRUE, sep = ";")
library(dplyr)
library(ggplot2)
data(film)

#movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"),c("Genre", "Rating", "Run")]

# Clean up the environment
Film_drama<- film %>%
  filter(Subject == "Drama")
```

*** =sample_code
```{r}

# Flm dataset is available in your workspace

# Calculate the Mean 


# Calculate the Standard Deviation


# Calculate the Minimum value


# Calculate the Maximum value


# Calculate the Median 


```

*** =solution
```{r}

# Flm dataset is available in your workspace

# Calculate the Mean 
mean(Film_drama$Length)

# Calculate the Standard Deviation
sd(Film_drama$Length)

# Calculate the Minimum value
min(Film_drama$Length)

# Calculate the Maximum value
max(Film_drama$Length)

# Calculate the Median 
median(Film_drama$Length)

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("mean", args = "object",
              not_called_msg = "You didn't call `mean()`!",
              incorrect_msg = "You didn't call `mean(object = ...)` with the correct argument, `object`.")

test_function("sd", args = "object",
              not_called_msg = "You didn't call `sd()`!",
              incorrect_msg = "You didn't call `sd(object = ...)` with the correct argument, `object`.")

test_function("min", args = "object",
              not_called_msg = "You didn't call `min()`!",
              incorrect_msg = "You didn't call `min(object = ...)` with the correct argument, `object`.")


test_function("max", args = "object",
              not_called_msg = "You didn't call `max()`!",
              incorrect_msg = "You didn't call `max(object = ...)` with the correct argument, `object`.")

test_function("median", args = "object",
              not_called_msg = "You didn't call `median()`!",
              incorrect_msg = "You didn't call `median(object = ...)` with the correct argument, `object`.")


test_error()
success_msg("Good work!")



```


