# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
setwd("C:/Users/Owner/Documents/DataScienceCertification/RepoResearch/peer1/RepData_PeerAssessment1")

df1<-read.csv(unz("activity.zip", "activity.csv"), colClasses=c("numeric","Date","numeric"))

# Check Dim
dim(df1)
```

```
## [1] 17568     3
```

## What is mean total number of steps taken per day?


```r
dfStepsPerDay<-aggregate(steps~date,data=df1,sum)
myMean<-summary(dfStepsPerDay$steps)[4]
myMedian<-summary(dfStepsPerDay$steps)[3]
summary(dfStepsPerDay$steps)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##      41    8840   10800   10800   13300   21200
```

```r
hist(dfStepsPerDay$steps,xlab="Steps Per Day",main="Histogram of Steps Per Day",col="blue")
```

![plot of chunk AveStepsPerDay](figure/AveStepsPerDay.png) 

The mean number of steps per day is 1.08 &times; 10<sup>4</sup>.  
The median number of steps per day is 1.08 &times; 10<sup>4</sup>.


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
