# Shares prediction

## Purpose
The purpose of this project is to show how you can build and use predictive models and automate Markdown reports. We used the OnlineNewsPopularity dataset
to then automate the EDA (exploratory data analysis) along with predictive modeling for the number of shares based on what data channel we are looking at.

## Required packages list

The following packages were required in this project:

`tidyverse`: an R package for data science, with tons of tools for data visualization, manipulation, and analysis

`caret`: Classification and Regression Training

`dplyr`: A tool for working with dataframes

`readr`: A tool to read in the file

`ggplot2`: A package to build graphs/visuals with

## Output Files
- The analysis for [social media is available here](Social%20Media%20Analysis.html)
- The analysis for [entertainment is available here](Entertainment Analysis.html)
- The analysis for [lifestyle is available here](Lifestyle Analysis.html)
- The analysis for [business is available here](Business Analysis.html)
- The analysis for [world is available here](World Analysis.html)
- The analysis for [technology is available here](Tech Analysis.html)


## Automation from Markdown

```{r,eval = FALSE}

library(tidyverse)
library(rmarkdown)
channelID<-list("data_channel_is_lifestyle",
             "data_channel_is_entertainment",
             "data_channel_is_bus",
             "data_channel_is_socmed",
             "data_channel_is_tech",
             "data_channel_is_world")

for (channel in c(0,1,2,3,4,5,6)){
  rmarkdown::render(
    "Project_2.Rmd",
    output_file=paste0( channelID[[channel+1]]),
    params = list(
    channel = channel,
    name = channelID[[channel+1]]
    )
  )
}
```



