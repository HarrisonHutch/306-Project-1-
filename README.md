---
title: "Project 1"
author: "GROUP MEMBERS"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
library(tidyverse)
library(lubridate)
```

## Overview

In the `data` directory of this project you will find the file from a paper published in *Nature Energy* titled [Natural gas savings in Germany during the 2022 energy crisis](https://www.nature.com/articles/s41560-023-01260-5). Here is the abstract of the article:

> Russia curbed its natural gas supply to Europe in 2021 and 2022, creating a grave energy crisis. This Article empirically estimates the crisis response of natural gas consumers in Germany—for decades, the largest export market for Russian gas. Using a multiple regression model, we estimate the response of small consumers, industry and power stations separately, controlling for the nonlinear temperature-heating relationship, seasonality and trends. We find significant and substantial gas savings for all consumer groups, but with differences in timing and size. For instance, industry started reducing consumption as early as September 2021, while small consumers saved substantially only since March 2022. Across all sectors, gas consumption during the second half of 2022 was 23% below the temperature-adjusted baseline. We discuss the drivers behind these savings and draw conclusions on their role in coping with the crisis.

Your job in this project falls into two categories:

1. A set of **tasks** that your group must complete exactly
2. A set of **objectives** that are more general in their approach.

## Tasks

### Task 1

* Load two files. To work in the console, use the `Session -> Set Working Directory -> To Source File Location`.
    * Call the first table `daily`: "./data/natural_gas_germany_daily.csv"
    * Call the second table `gas`: "./data/dutch_ttf_natural_gas.csv". Be sure to properly import the `Date` column.
    * Demonstrate that these have been loaded by showing the number of rows and columns in each table.
  

### Task 2

* The data in `daily` are collected over days, with information on different types of natural gas consumption (`consumption_small`, `consumption_industry`, `consumption_power`). Provide summaries of typical values for each of these three types of consumption.


### Task 3

Answer some questions about the data in `daily`:

* How many weeks do the data cover?
* What is the percentage change in the `consumption_*` variables (that is the last day minus the first day divided by the first day)?
* What proportion of the days are marked as holidays?
* For each month in each year, what was the year-month combination with the lowest median `consumption_power` value?
   
### Task 4

* The original paper aggregated the data to monthly means for each consumption type in `daily` and the `Price` column of `gas` to produce the following image:<br/>
![Original consumption by month graph](proj1fig1.png)<br/>
Produce plots that show the same information that is presented in this plot. Your plots do not have to have the same colors or markings, but we should be able to use them to compare the trends for the three price variables. 

### Task 5

* Write a predicate function that returns true if any value in vector is missing. Use this function to find columns with missing values in the `daily` column. Create a plot or table that shows how often patterns of missingness occur: are all of the missing values in the same rows or are the various columns missing data in different ways?



### Task 6

* Limit the `gas` table to days where the price exceeded the yearly median. Use the concept of [circular means](https://en.wikipedia.org/wiki/Circular_mean) to compute the average day of the year when price exceeds the yearly median price. The `yday` function will likely be useful here. 


### Task 7

* Using the cut function, create two nominal variables from quantitative data in the `daily` dataset. Use these groups to summarize the data. Use arrange to show the smallest or largest values in these comparisons.

### Task 8

* There are several variables that pull out data by different industry (the `_idx` columns). Create a table for these columns using `select` and the `ends_with` function. Provide two different plots that show of the relations between these variables (you do not need to have all variables in each plot).


## Objectives

### Objective 1

* Produce at least five more figures. For each figure, write a brief caption explaining the plot and what you have learned from the plot. Each figure should attempt to provide new insight into the data set not included elsewhere
    * A marginal distribution
    * A joint distribution
    * A plot of a summary measure such as a conditional mean
    * A plot using `facet_wrap` or `facet_grid`
    * A plot that shows seasonal effects before the crisis (September 2021 until October 2022)
    

### Objective 2

* Compare and contrast holidays and non-holidays for household energy consumption. Select 3 ways of comparing these groups. Provide at least one graph.

### Objective 3

* According to the paper, the gas crisis occurred between September 2021 until October 2022. Compare this period with the periods before and after on household and industrial consumption. Write a paragraph explaining your findings.


### Objective 4

* Explore the [documentation for ggplot](https://ggplot2.tidyverse.org/). Select one geometery and one `stat_` function we have not used before or use an option to a previously used geometry/stat with a new option. Write a short paragraph explaining what the plots show. 

### Objective 4

* Investigate solar radiation's marginal distribution and also it's relationship with temperature.


### Objective 5

* Use `group_by` to summarize by a new feature of this data set not otherwise discussed in the tasks or objectives. What have you learned with these investigation?

### Objective 6

* Based on your exploration of the data, suggest three questions that could be asked from these data or additional data that you can imagine. Be sure to explain why the previous plots or calculations indicates that this would be an interesting our useful exploration.

### Objective 7

* Write an abstract for your project. Briefly explain what you did, what you found, and why a potential reader should be interested in your research.
