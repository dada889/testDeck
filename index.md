---
title       : My Shinyapp
subtitle    : the app for Monthly Airline Passenger Numbers 1949-1960
author      : htt       
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

1. My shiny app study on the data of Monthly Airline Passenger Numbers 1949-1960
2. The data set is The classic Box & Jenkins airline data. Monthly totals of international airline passengers, 1949 to 1960.
3. This data set is a monthly time series data include 144 observation.
4. The shiny app can plot the selected data.
5. The shiny app can do the prediction using time series model.

--- .class #id 

## The time series data
The graph plot the data. we can see there is a time series pattern for this data.
![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 




---
## The predicton

* I use Holt-Winters Filtering model to do the prediction
* Holt-Winters exponential smoothing with trend and additive seasonal component.

Smoothing parameters:
 alpha: 0.2479595
 beta : 0.03453373
 gamma: 1

The additive Holt-Winters prediction function (for time series with period length p) is

Yhat[t+h] = a[t] + h * b[t] + s[t - p + 1 + (h - 1) mod p],

where a[t], b[t] and s[t] are given by

a[t] = α (Y[t] - s[t-p]) + (1-α) (a[t-1] + b[t-1])

b[t] = β (a[t] - a[t-1]) + (1-β) b[t-1]

s[t] = γ (Y[t] - a[t]) + (1-γ) s[t-p]

---
## The plot of the prediction 
* I predict 100 month ahead data and plot the result.
* In the plot, we can see the predicted data follow the similar pattern of real data.
![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 
