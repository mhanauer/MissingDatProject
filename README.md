---
title: "Power Analysis in R for Multilevel Models"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Here we are reading in each data file naming them data1:total.  See what happens when there is missing data.
```{r}
setwd("~/Box Sync/Unreviewed Excel Training Data/ Matt'sExcelTraining Data")
library(XLConnect)
setwd("~/Box Sync/Unreviewed Excel Training Data/ Matt'sExcelTraining Data")
data1 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data1) = c("gender", "sexorien", "age", "eth")
head(data1)
data1$site = rep(1,length(data1$gender))

data2 = readWorksheetFromFile("Meadows Hospital Lunch & Learn.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data2) = c("gender", "sexorien", "age", "eth")
head(data2)
data2$site = rep(1,length(data2$gender))



data3 = readWorksheetFromFile("Merriville Training 7272016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data3) = c("gender", "sexorien", "age", "eth")
head(data3)
data3 = data3[-1,]
data3$site = rep(1,length(data3$gender))


data4 = readWorksheetFromFile("NASW Conference.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data4) = c("gender", "sexorien", "age", "eth")
head(data4)
data4$site = rep(1,length(data4$gender))


data5 = readWorksheetFromFile("Pride Board Training 7142016.xlsx", sheet = 1, startCol = 1, endCol = 4)
colnames(data5) = c("gender", "sexorien", "age", "eth")
head(data5)
data5$site = rep(1,length(data5$gender))


data6 = readWorksheetFromFile("Spencer Pride Training (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data6) = c("gender", "sexorien", "age", "eth")
head(data6)
data6$site = rep(1,length(data6$gender))


data7 = readWorksheetFromFile("Terre Haute 7272016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data7) = c("gender", "sexorien", "age", "eth")
head(data7)
data7$site = rep(1,length(data7$gender))



data8 = readWorksheetFromFile("Youth Services Association Administraiont 9012016.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data8) = c("gender", "sexorien", "age", "eth")
head(data8)
data8$site = rep(1,length(data8$gender))


data9 = readWorksheetFromFile("Youth Services Association Session 2 .xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data9) = c("gender", "sexorien", "age", "eth")
head(data9)
data9$site = rep(1,length(data9$gender))


data10 = readWorksheetFromFile("Youth Services Bureau 7-29-16 (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data10) = c("gender", "sexorien", "age", "eth")
head(data10)
data10$site = rep(1,length(data10$gender))


data11 = readWorksheetFromFile("Youth Services Bureau 7-29-16 (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data11) = c("gender", "sexorien", "age", "eth")
head(data11)
data11$site = rep(1,length(data11$gender))


data12 = readWorksheetFromFile("Ivy Tech 2017 Training.xlsx", sheet = 1, startCol = 2, endCol = 5)
colnames(data12) = c("gender", "sexorien", "age", "eth")
head(data12)
data12$site = rep(1,length(data12$gender))


data13 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data13) = c("gender", "sexorien", "age", "eth")
head(data13)
data13 = data13[-1,]
data13$site = rep(1,length(data13$gender))


data14 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data14) = c("gender", "sexorien", "age", "eth")
head(data14)
data14$site = rep(1,length(data14$gender))


data15 = readWorksheetFromFile("IU Pre School Training 12716.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data15) = c("gender", "sexorien", "age", "eth")
head(data15)
data15 = data15[-1,]
data15$site = rep(1,length(data15$gender))



data16 = readWorksheetFromFile("ISCA Fall 2015.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data16) = c("gender", "sexorien", "age", "eth")
head(data16)
data16 = data16[-1,]
data16$site = rep(1,length(data16$gender))


data17 = readWorksheetFromFile("Indiana School Health Conference.xlsx", sheet = 1, startCol = 2, endCol = 5)
colnames(data17) = c("gender", "sexorien", "age", "eth")
head(data17)
data17$site = rep(1,length(data17$gender))


data18 = readWorksheetFromFile("Boys + Girls Club Camp Training 2016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data18) = c("gender", "sexorien", "age", "eth")
head(data18)
data18 = data18[-1,]
data18$site = rep(1,length(data18$gender))


data19 = readWorksheetFromFile("Allied Media Conference.xlsx", sheet = 1, startCol = 1, endCol = 4)
colnames(data19) = c("gender", "sexorien", "age", "eth")
head(data19)
data19$site = rep(1,length(data19$gender))


data20 = readWorksheetFromFile("Janet Decker Law Class.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data20) = c("gender", "sexorien", "age", "eth")
head(data20)
data20$site = rep(1,length(data20$gender))


data21 = readWorksheetFromFile("Janet Decker Law Class.xlsx", sheet = 2, startCol = 4, endCol = 7)
colnames(data21) = c("gender", "sexorien", "age", "eth")
head(data21)
data21$site = rep(1,length(data21$gender))


data22 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 2, startCol = 3, endCol = 6)
colnames(data22) = c("gender", "sexorien", "age", "eth")
head(data22)
data22$site = rep(1,length(data22$gender))


data23 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 4, endCol = 7)
colnames(data23) = c("gender", "sexorien", "age", "eth")
head(data23)
data23$site = rep(1,length(data23$gender))


data24 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 3, startCol = 5, endCol = 8)
colnames(data24) = c("gender", "sexorien", "age", "eth")
head(data24)
data24$site = rep(1,length(data24$gender))

```
Now we need to investigate the missing data (did it include "blanks") and add a site variable indicator
```{r}

```
Then we need to 

