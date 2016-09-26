---
title       : Chapter 2 
description : Film Data
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:fee7a4f081
## What type of movie has the most counts?

Have a look at the plot that showed up in the viewer to the right. Which type of movie has the  most counts?

*** =instructions
- Drama
- Action
- Western
- War

*** =hint



*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

film <- read.csv("http://s3.amazonaws.com/data415/film.csv", header = TRUE, sep = ";")


#load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/all_wars_matrix.RData"))
library(ggplot2)
ggplot(data =film, aes(film$Subject)) + geom_bar() + ggtitle("Movies by Subjects") + xlab("Subjects ")

```
*** =sct
```{r, eval=FALSE}

test_mc(correct = 1, 
        feedback_msgs = c("Correct.",
                          "Incorrect.",
                          "Incorrect",
                          "Incorrect"))


```

--- type:NormalExercise lang:r xp:100 skills:1 key:b2a65d2d17
## Digging Deeper into the Drama category

In the previous exercise, you saw a histogram graphed for counts of Films. 
In this exercise, we'll have a look at the Drama category !

A dataset with a selection of movies, `film`, is available in the workspace.

*** =instructions
- Check out the structure of `film'. 
- Select movies with a rating of 5 or higher. Assign the result to `good_movies`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code

library(dplyr)
library(ggplot2)
data(Films)
#movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"),c("Genre", "Rating", "Run")]

# Clean up the environment
Film_drama<- film %>%
  filter(Subject == "Drama")
```

*** =sample_code
```{r}

# Flm dataset is available in your workspace

# Check out the structure of movie_selection


```

*** =solution
```{r}

# Flm dataset is available in your workspace

# Check out the structure of film drama
str(Film_drama)



```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")
test_error()

success_msg("Good work!")
```
