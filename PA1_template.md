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

```r
## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
```
