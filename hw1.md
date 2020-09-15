Untitled
================

# Problem 1

# create a data frame

library(tidyverse)

df1 = tibble( vec\_numeric = rnorm(10), vec\_char = c(“a”, “b”, “c”,
“d”, “e”, “f”, “g”, “h”, “i”, “j”), vec\_logical = random\_sample \>
0, vec\_factor = factor(c(“A”, “B”, “C”, “A”, “B”, “C”, “A”, “B”, “C”,
“A”)))

df1

# take the mean of each variable

vec\_numeric = rnorm(10) vec\_numeric\_mean = mean(vec\_numeric)

vec\_char = c(“a”, “b”, “c”, “d”, “e”, “f”, “g”, “h”, “i”, “j”)
vec\_char\_mean = mean(vec\_char)

vec\_logical = random\_sample \> 0 vec\_logical\_mean = vec\_logical

vec\_factor = factor(c(“A”, “B”, “C”, “A”, “B”, “C”, “A”, “B”, “C”, “A”)
vec\_factor\_mean =
mean(vec\_factor)

# it works for numeric vector but not for lofical vector, character vector, or factor vector

# convert logical vector to numeric, and multiply the random sample by the result

vec\_logical\_num = as.numeric(vec\_logical) l = vec\_logical\_num \*
random\_sample

# convert logical vector to a factor, and multiply the random sample by the result

vec\_logical\_factor = as.factor(vec\_logical) f = vec\_logical\_factor
\* random\_sample \# cannot multiply a factor vector to a numeric
factor

# convert logical vector to a factor and then convert the result to numeric, and multiply the random sample by the result

vec\_logical\_factor\_num = as.numeric(vec\_logical\_factor) n =
vec\_logical\_factor\_num \* random\_sample

# Problem 2

data(“penguins”, package = “palmerpenguins”)

nrow(penguins) ncol(penguins)

flipper\_length\_mean = mean(penguins$flipper\_length\_mm, na.rm =
TRUE)

# The data frame recorded information including species, island, bill length, bill depth, flipper length, body mass, and sex of 344 penguins from 2007 to 2009.

# Excluding missing records, the mean flipper length of penguins is 200.9152 mm.

ggplot(penguins, aes(x = bill\_length\_mm, y = flipper\_length\_mm,
color = species)) + geom\_point()

ggsave(“scatterplot 1.pdf”)
