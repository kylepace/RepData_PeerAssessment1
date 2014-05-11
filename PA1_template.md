# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
unzip("./activity.zip")
acts <- read.csv("./activity.csv", colClasses = c("integer", "Date", "integer"))
```



## What is mean total number of steps taken per day?

```r
actsNoStepNa <- acts[!is.na(acts$steps), ]
byDay <- aggregate(actsNoStepNa$steps, by = list(actsNoStepNa$date), sum)
hist(byDay$x, xlab = "Total Steps Per Day")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

```r
mean(byDay$x)
```

```
## [1] 10766
```

```r
median(byDay$x)
```

```
## [1] 10765
```



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
