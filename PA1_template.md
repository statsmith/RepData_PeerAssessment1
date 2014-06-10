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


```r
dfStepsPerInterval<-aggregate(steps~interval,data=df1,mean)
maxStepsInterval<-dfStepsPerInterval[dfStepsPerInterval$steps==max(dfStepsPerInterval$steps),]
maxInterval<-maxStepsInterval[1]
maxSteps<-round(maxStepsInterval[2],0)


plot(dfStepsPerInterval$steps~dfStepsPerInterval$interval,type="l",col="blue",
     ylab="Mean Number of Steps",xlab="Interval",main="Mean Steps Per Interval")
```

![plot of chunk MaxInterval](figure/MaxInterval.png) 

The 5-minute interval, on average across all the days in the dataset, containing the maximum number of steps is interval 835.   
The mean number of steps in this interval is 206.



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
