---
title: "Missing Data Project"
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


data9 = readWorksheetFromFile("Youth Services Association Session 2.xlsx", sheet = 1, startCol = 3, endCol = 6)
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


data = rbind(data1, data2, data3, data4, data5, data6, data7, data8, data9, data10, data11, data12, data13, data14, data15, data16, data17, data18, data19, data20, data21, data22, data23, data24)
data = as.data.frame(data)
head(data)
dim(data)
```
Now we need to start transforming them into the codes that I created.  First we need to through and get rid of all data that doesn't make sense.  There is an error or if I cannot make any sense from the reponse. 

```{r}

genderLevels = as.factor(data$gender)
levels(genderLevels)

ageLevels = as.factor(data$age)
levels(ageLevels)

ethLevels = as.factor(data$eth)
levels(ethLevels)
```
Now I need to get rid of the ones I cannot make sense of.  Change them t0 -9 and then omit:

Gender = -9,"Professor"

Sexorien = "\"Left\"", "\"F\"", "\"Woman\"", "\"I date men only\"", "\"F\"", "\"Ø\"","\"Yes\"" , "\"M\"", "I'd need to know you better to share that =)", "\"Happily married\"", "\"MYOB\"", "(I?)" , "\"Married to a man\"", "~ ? ~ " 

Age = "\"?\"", "\"50+\"", "\"Old\"", "40 and fabulous", "No Pre", "\"60+\"", "\"2\"", "45+", "over 21", "\"30+\"", "\"Guess\"", "Illegible", "range 22-68", "\"4\"", "\"MYOB\"", "\"40ish\"", "\"Ø\""

eth =  "\"?\"" 
```{r}
dataGender = ifelse(data$gender == "Professor", -9, ifelse(data$gender == "Straight", -9, ifelse(data$gender =="Nb", -9,  data$gender)))
genderLevels = as.factor(dataTest)
levels(genderLevels)

dataSexOrien = ifelse(data$sexorien == "\"Left\"", -9, ifelse(data$sexorien == "\"F\"", -9, ifelse(data$sexorien == "\"Woman\"", -9, ifelse( data$sexorien == "\"I date men only\"", -9, ifelse( data$sexorien == "\"I date men only\"", -9, ifelse(data$sexorien == "\"F\"", -9, ifelse(data$sexorien == "\"Ø\"", -9, ifelse(data$sexorien == "\"Yes\"", -9, ifelse(data$sexorien == "\"M\"", -9, ifelse(data$sexorien ==  "I'd need to know you better to share that =)", -9, ifelse(data$sexorien == "\"Happily married\"",-9, ifelse(data$sexorien == "\"MYOB\"" , -9, ifelse( data$sexorien == "(I?)", -9, ifelse( data$sexorien == "~ ? ~ " , -9, ifelse(data$sexorien == "\"Male\"", -9, ifelse(data$sexorien == "[Crossed something out]", -9, ifelse(data$sexorien == "\"Married to a man\"", -9, ifelse(data$sexorien == "F", -9, ifelse(data$sexorien == "h", -9, ifelse(data$sexorien == "H", -9, ifelse(data$sexorien == "Female",-9, ifelse(data$sexorien == "She" , -9, ifelse(data$sexorien == "Single", -9, ifelse(data$sexorien == "\"Female\"", -9, ifelse(data$sexorien == "L", -9, ifelse(data$sexorien == "M", -9, ifelse(data$sexorien == "\"Feminine\"", -9, ifelse(data$sexorien == "Male", -9,data$sexorien))))))))))))))))))))))))))))
sexOrienLevels = as.factor(dataSexOrien)
levels(sexOrienLevels)


dataAge = ifelse(data$age == "\"?\"", -9, ifelse(data$age == "\"50+\"", -9,ifelse(data$age == "\"Old\"", -9, ifelse(data$age == "40 and fabulous",-9,ifelse(data$age == "No Pre", -9, ifelse(data$age == "\"60+\"", -9, ifelse(data$age == "\"2\"", -9, ifelse(data$age == "45+", -9, ifelse(data$age == "over 21", -9, ifelse(data$age == "\"30+\"", -9,ifelse(data$age == "\"Guess\"", -9, ifelse(data$age == "Illegible", -9, ifelse(data$age == "range 22-68", -9, ifelse(data$age == "\"4\"", -9, ifelse(data$age == "\"MYOB\"", -9, ifelse(data$age == "\"40ish\"", -9, ifelse(data$age == "\"Ø\"", -9,data$age )))))))))))))))))


dataEth = ifelse(data$eth == "\"?\"", -9, ifelse(data$eth == "\"Ø\"" , -9, data$eth))
ethLevels = as.factor(dataEth)
levels(ethLevels)
```
Here needed to get rid of the ones I cannot make sense of and then also transform the missing into one code "MIssing"

```{r}
data1 = cbind(dataGender, dataSexOrien, dataAge, dataEth, data$site)
data1 = ifelse(data1 == "NA", "Missing", ifelse(data1 == -9, NA, ifelse(data1 == "Blank", "Missing", ifelse( data1 == "N/A", "Missing", ifelse(data1 == "Flank", "Missing",ifelse(data1 == "MIssing", "Missing", data1))))))
data1 = as.data.frame(data1)
head(data1)
data1 = na.omit(data1)
sum(is.na(data1))
data1 = as.data.frame(data1)
dim(data1)
head(data1)
data2 = data1[,1:4]
head(data2)
head(data1)
site = data1$V5
site = as.data.frame(site)
data1 =  cbind(data2, site)
head(data1)
colnames(data1) = c("gender", "sexorien", "age", "eth", "site")
head(data1)
dim(data1)
```
Now I need to create a female, otherGI (GI = gender identity), straight (reference is everything else), white, black, hispanic, multiracial, AI, otherEI (EI = ethnic identity)

"Female/masculine" = coded this a otherGender

"[Crossed something out]" = coded this as otherGender maybe include this as a missing data code
```{r}
female = ifelse(data1$gender == "\"Female-->sex, androgyne/butch, top/bottom\"", 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "F.", 1, ifelse(data1$gender =="Femal",1, ifelse(data1$gender == "Female", 1, ifelse(data1$gender == "Female (Cisgender)", 1, ifelse(data1$gender == "Female/she", 1, ifelse(data1$gender == "Femele", 1, ifelse(data1$gender == "Lady" , 1, ifelse(data1$gender == "Woman", 1, ifelse(data1$gender == "\"Female--cisgender\"", 1, ifelse(data1$gender == "\"She\"", 1, ifelse(data1$gender == "[Female symbol]" , 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "F", 1, ifelse(data1$gender == "Famel",1, ifelse(data1$gender == "Female (cis)", 1, ifelse(data1$gender == "Female/Woman", 1, ifelse(data1$gender == "She, her, hers Female", 1, ifelse(data1$gender == "woman", 1, ifelse(data1$gender =="Woman (she/her)", 1, ifelse(data1$gender == "female", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "Missing", "Missing", 0)))))))))))))))))))))))))

genderLevels = as.factor(data1$gender)
levels(genderLevels)

otherGI = ifelse(data1$gender == "[Crossed something out]", 1, ifelse(data$gender == "om", 1,ifelse(data1$gender == "Non-binary", 1, ifelse(data1$gender == "Genderqueer", 1, ifelse(data1$gender == "Non-binary", 1, 0)))))

head(otherGI)
sum(otherGI)

sexorienLevels = as.factor(data1$sexorien)
levels(sexorienLevels)

straight = ifelse(data1$sexorien ==  "\"Female-> like males\"" , 1, ifelse(data1$sexorien == "\"Straight?\"", 1, ifelse(data1$sexorien == "[Crossed something out] Straight", 1, ifelse(data1$sexorien == "Herdosexual/Straight" , 1, ifelse(data1$sexorien == "hetero", 1, ifelse(data1$sexorien == "Heterosexual", 1, ifelse(data1$sexorien == "Hetero/Cisgender", 1, ifelse(data1$sexorien == "Male-heterosexual",1, ifelse(data1$sexorien == "Married-Hetero", 1, ifelse(data1$sexorien == "Staight" , 1, ifelse(data1$sexorien == "Straight",1, ifelse(data1$sexorien == "Straight Heterosexual", 1, ifelse(data1$sexorien == "Straight/hetero", 1, ifelse(data1$sexorien == "Strait", 1, ifelse(data1$sexorien == "\"Straight/Ally\"", 1, ifelse(data1$sexorien == "[Crossed out \"Stright\"] Stright", 1, ifelse(data1$sexorien == "heter-", 1, ifelse(data1$sexorien == "hetero ", 1, ifelse(data1$sexorien == "Male/Female Traditional Choice", 1, ifelse(data1$sexorien == "s", 1, ifelse(data1$sexorien =="Straght", 1, ifelse(data1$sexorien == "straight " , 1, ifelse(data1$sexorien == "Straight married", 1, ifelse(data1$sexorien == "Straight/Heterosexual", 1, ifelse(data1$sexorien == "streight", 1, ifelse(data1$sexorien == "Hetero/Cisgender" ,1, ifelse(data1$sexorien == "married straight cisender", 1, ifelse(data1$sexorien == "S", 1, ifelse(data1$sexorien =="straight" , 1, ifelse(data1$sexorien == "Straight (Cisgender)", 1, ifelse(data1$sexorien == "Straight.", 1, ifelse(data1$sexorien == "strait", 1, ifelse(data1$sexorien == "Traditional", 1, ifelse(data1$sexorien == "\"F Hetero\"", 1, ifelse(data1$sexorien =="\"Hetero-Female\"", 1, ifelse(data1$sexorien == "\"Straight/ally\"" , 1, ifelse(data1$sexorien == "[Crossed out \"Femal\"] Heterosexual", 1, ifelse(data1$sexorien == "Heteroflexible", 1, ifelse(data1$sexorien == "heterosexual [crossed out straight]", 1, ifelse(data1$sexorien == "Male-heterosexual", 1, ifelse(data1$sexorien == "Straight Heterosexual" , 1, 0)))))) )))))))))))))))))))))))))))))))))))

ethLevels = as.factor(data1$eth)
levels(ethLevels)
white = 



```


