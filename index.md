---
title       : Fred's Slides
subtitle    : 
author      : Fred Hope
job         : Data Scientist
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

--- .class #id

Bodyweight over time

![plot of chunk unnamed-chunk-1](assets/fig/unnamed-chunk-1-1.png) 

---

Job Application Status


```r
info <- readLines("~/Documents/Job Apps.txt")
info <- gsub("\t\t*","\t",info)
con <- textConnection(info)
jobs <- read.delim(con)
close(con)

totalapps <- nrow(jobs)
accepted <- sum(jobs$Status=="follow-up")
rejected <- sum(jobs$Status=="rejected")
pending <- totalapps - accepted - rejected
```


```r
cat("Job Apps (success-rejected-pending):"); paste(accepted,rejected,pending,sep="-")
```

```
## Job Apps (success-rejected-pending):
```

```
## [1] "0-2-24"
```
