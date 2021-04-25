---
title: "Reproducible Research: Peer Assessment 1"
output: 
  html_document:
    keep_md: true
---


## Loading and preprocessing the data

Loading libraries:


```r
library(readr)
library(ggplot2)
```

The following settings are local-environment dependent so they have to be 
adjusted according to the local computer settings.


```r
# Folder with the cloned repository
project_folder = "D:/projects/RepData_PeerAssessment1"
```

Code responsible for unzipping the archive and reading the data:


```r
original_folder = getwd()
setwd(project_folder)

unzip("activity.zip", overwrite = TRUE, exdir = ".")

original_data <- read_delim("activity.csv", 
                           skip = 1,
                           delim = ",",
                           col_names = c("steps", "date", "interval"),
                            col_types = cols(
                              steps = col_integer(),
                              date = col_date(format= "%Y-%m-%d"),
                              interval = col_factor()) 
                           )
summary(original_data)
```

```
##      steps             date               interval    
##  Min.   :  0.00   Min.   :2012-10-01   0      :   61  
##  1st Qu.:  0.00   1st Qu.:2012-10-16   5      :   61  
##  Median :  0.00   Median :2012-10-31   10     :   61  
##  Mean   : 37.38   Mean   :2012-10-31   15     :   61  
##  3rd Qu.: 12.00   3rd Qu.:2012-11-15   20     :   61  
##  Max.   :806.00   Max.   :2012-11-30   25     :   61  
##  NA's   :2304                          (Other):17202
```


## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
