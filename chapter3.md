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
Film_clean<- film %>%
  group_by(Length)%>%
  filter(!is.na(Length))
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
mean(Film_clean$Length)

# Calculate the Standard Deviation
sd(Film_clean$Length)

# Calculate the Minimum value
min(Film_clean$Length)

# Calculate the Maximum value
max(Film_clean$Length)

# Calculate the Median 
median(Film_clean$Length)

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_student_typed("mean(Film_clean$Length)", not_typed_msg = "You didn't call ggplot.")
test_student_typed("sd(Film_clean$Length)", not_typed_msg = "You didn't call ggplot.")
test_student_typed("min(Film_clean$Length)", not_typed_msg = "You didn't call ggplot.")
test_student_typed("max(Film_clean$Length)", not_typed_msg = "You didn't call ggplot.")
test_student_typed("median(Film_clean$Length)", not_typed_msg = "You didn't call ggplot.")

test_error()
success_msg("Good work!")



```


