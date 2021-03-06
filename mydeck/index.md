---
title       : Course Project Developing Data Products
subtitle    : mtcars Apps
author      : SN Jalis
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Overview

For this project, I have developed a Shiny Application for use with the mtcars data package in R. I've encountered this data during the Module 7: Regression Model which can be sourced from [here](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/mtcars.html)

---

## Objective

*mtcars Apps* allows the user to drill down the features of the chosen car. The apss will also show the mean value of the chosen car feature across all of the records associated with the chosen car manufacturer. 

The apps is indeed simple but may be resourceful as more manufacturers being added in the database.

---

## Development 

1. Extract the car manufacturer from the row names of the mtcars data using below code and saved in the server.R file:

```r
library(datasets)
data(mtcars)

#Extract the row names as a column in the dataset
mtcars$makemodel <- rownames(mtcars)

#Extract the manufacturer/make from the rownames
mtcars$make <- gsub( " .*$", "", mtcars$makemodel)
```

2. The mean value was then derived in the way shown below. The variables "make" and "feature" in the code below represent the input values selected by the application user:

```r
make <- "Mazda"
feature <- "qsec"

data <- mtcars[mtcars$make==make,feature]
paste("The mean value of",feature,"for",make,"cars is",print(mean(data)))
```

---

## Viewing and Running the mtcars App

The shiny application I developed has been published to the Shiny server at the following [Link](https://trexdg.shinyapps.io/DDPProject)

---
