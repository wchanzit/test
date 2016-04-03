# PA1_template
Warren Chanzit  
April 3, 2016  

## Pre-Analysis set-up.
### Import packages and set working directory.

```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
library(ggplot2)
library(reshape2)
```

### Read and process data.

```r
data <- read.csv("activity.csv")
data$date <- as.Date(data$date)
data2 <- na.omit(data)
```

## Calculate and plot total steps per day.

```r
daySteps <- with(data2, tapply(steps, date, sum))
hist(daySteps,
     breaks = 10,
     xlab = "Steps",
     main = "Daily Steps Taken")
```

![](test_files/figure-html/unnamed-chunk-3-1.png)
