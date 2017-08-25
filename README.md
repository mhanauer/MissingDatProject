---
title: "Missing Data Project"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Here we are reading in each data file naming them data1:total.  See what happens when there is missing data.

The following organizations had two sesstions Youth Services Association, IUSSW Alumni Conference , Janet Decker Law Class, and MCCSC had three sessions.  I data12 is missing there so there are 22 total excel documents with 5 duplicates therefore there are 17 unique sites visited with 22 total programs provided to 1041 people.
```{r}
setwd("~/Box Sync/Unreviewed Excel Training Data/ Matt'sExcelTraining Data")
library(XLConnect)
data1 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data1) = c("gender", "sexorien", "age", "eth")
head(data1)
data1$site = rep(1,length(data1$gender))

data2 = readWorksheetFromFile("Meadows Hospital Lunch & Learn.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data2) = c("gender", "sexorien", "age", "eth")
head(data2)
data2$site = rep(2,length(data2$gender))



data3 = readWorksheetFromFile("Merriville Training 7272016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data3) = c("gender", "sexorien", "age", "eth")
head(data3)
data3 = data3[-1,]
data3$site = rep(3,length(data3$gender))


data4 = readWorksheetFromFile("NASW Conference.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data4) = c("gender", "sexorien", "age", "eth")
head(data4)
data4$site = rep(4,length(data4$gender))


data5 = readWorksheetFromFile("Pride Board Training 7142016.xlsx", sheet = 1, startCol = 1, endCol = 4)
colnames(data5) = c("gender", "sexorien", "age", "eth")
head(data5)
data5$site = rep(5,length(data5$gender))


data6 = readWorksheetFromFile("Spencer Pride Training (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data6) = c("gender", "sexorien", "age", "eth")
head(data6)
data6$site = rep(6,length(data6$gender))


data7 = readWorksheetFromFile("Terre Haute 7272016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data7) = c("gender", "sexorien", "age", "eth")
head(data7)
data7$site = rep(7,length(data7$gender))


data8 = readWorksheetFromFile("Youth Services Association Administraiont 9012016.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data8) = c("gender", "sexorien", "age", "eth")
head(data8)
data8$site = rep(8,length(data8$gender))


data9 = readWorksheetFromFile("Youth Services Association Session 2.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data9) = c("gender", "sexorien", "age", "eth")
head(data9)
data9$site = rep(9,length(data9$gender))



data10 = readWorksheetFromFile("Youth Services Bureau 7-29-16 (Created by Piper; Edited by Brie).xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data10) = c("gender", "sexorien", "age", "eth")
head(data10)
data10$site = rep(10,length(data10$gender))


data11 = readWorksheetFromFile("Ivy Tech 2017 Training.xlsx", sheet = 1, startCol = 2, endCol = 5)
colnames(data11) = c("gender", "sexorien", "age", "eth")
head(data11)
data11$site = rep(11,length(data11$gender))


data13 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data13) = c("gender", "sexorien", "age", "eth")
head(data13)
data13 = data13[-1,]
data13$site = rep(13,length(data13$gender))

data14 = readWorksheetFromFile("IUSSW Alumni Conference.xlsx", sheet = 2, startCol = 3, endCol = 6)
colnames(data14) = c("gender", "sexorien", "age", "eth")
head(data14)
data14 = data14[-1,]
data14$site = rep(13,length(data14$gender))

data15 = readWorksheetFromFile("IU Pre School Training 12716.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data15) = c("gender", "sexorien", "age", "eth")
head(data15)
data15 = data15[-1,]
data15$site = rep(15,length(data15$gender))



data16 = readWorksheetFromFile("ISCA Fall 2015.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data16) = c("gender", "sexorien", "age", "eth")
head(data16)
data16 = data16[-1,]
data16$site = rep(16,length(data16$gender))


data17 = readWorksheetFromFile("Indiana School Health Conference.xlsx", sheet = 1, startCol = 2, endCol = 5)
colnames(data17) = c("gender", "sexorien", "age", "eth")
head(data17)
data17$site = rep(17,length(data17$gender))


data18 = readWorksheetFromFile("Boys + Girls Club Camp Training 2016.xlsx", sheet = 1, startCol = 4, endCol = 7)
colnames(data18) = c("gender", "sexorien", "age", "eth")
head(data18)
data18 = data18[-1,]
data18$site = rep(18,length(data18$gender))


data19 = readWorksheetFromFile("Allied Media Conference.xlsx", sheet = 1, startCol = 1, endCol = 4)
colnames(data19) = c("gender", "sexorien", "age", "eth")
head(data19)
data19$site = rep(19,length(data19$gender))


data20 = readWorksheetFromFile("Janet Decker Law Class.xlsx", sheet = 1, startCol = 3, endCol = 6)
colnames(data20) = c("gender", "sexorien", "age", "eth")
head(data20)
data20$site = rep(20,length(data20$gender))


data21 = readWorksheetFromFile("Janet Decker Law Class.xlsx", sheet = 2, startCol = 4, endCol = 7)
colnames(data21) = c("gender", "sexorien", "age", "eth")
head(data21)
data21$site = rep(21,length(data21$gender))


data22 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 2, startCol = 4, endCol = 7)
colnames(data22) = c("gender", "sexorien", "age", "eth")
head(data22)
data22$site = rep(22,length(data22$gender))


data23 = readWorksheetFromFile("MCCSC LGBTQA+ Competency Training_assessment data.xlsx", sheet = 3, startCol = 5, endCol = 8)
colnames(data23) = c("gender", "sexorien", "age", "eth")
head(data23)
data23$site = rep(23,length(data23$gender))


data = rbind(data1, data2, data3, data4, data5, data6, data7, data8, data9, data10, data11, data13, data14, data15, data16, data17, data18, data19, data20, data21, data22, data23)
data = as.data.frame(data)
head(data)
dim(data)

```
Here is a list of all the codes that I could not make sense of and therefore deleted for the following variables gender = dataGender; sex orientation = dataSexOrien; age = dataAge; ethnicity = dataEth.

For example in the dataGender variable, I could not figure out how to categorize "Professor"; therefore, I gave it the value -9, which means it will be deleted.

If you can make sense of these options and place them into categories please let me know and I can make the changes.
```{r}
dataGender = ifelse(data$gender == "Professor", -9, ifelse(data$gender == "Straight", -9, ifelse(data$gender =="Nb", -9,  data$gender)))

dataSexOrien = ifelse(data$sexorien == "\"Left\"", -9, ifelse(data$sexorien == "\"F\"", -9, ifelse(data$sexorien == "\"Woman\"", -9, ifelse( data$sexorien == "\"I date men only\"", -9, ifelse( data$sexorien == "\"I date men only\"", -9, ifelse(data$sexorien == "\"F\"", -9, ifelse(data$sexorien == "\"Ø\"", -9, ifelse(data$sexorien == "\"Yes\"", -9, ifelse(data$sexorien == "\"M\"", -9, ifelse(data$sexorien ==  "I'd need to know you better to share that =)", -9, ifelse(data$sexorien == "\"Happily married\"",-9, ifelse(data$sexorien == "\"MYOB\"" , -9, ifelse( data$sexorien == "(I?)", -9, ifelse( data$sexorien == "~ ? ~ " , -9, ifelse(data$sexorien == "\"Male\"", -9, ifelse(data$sexorien == "[Crossed something out]", -9, ifelse(data$sexorien == "\"Married to a man\"", -9, ifelse(data$sexorien == "F", -9, ifelse(data$sexorien == "h", -9, ifelse(data$sexorien == "H", -9, ifelse(data$sexorien == "Female",-9, ifelse(data$sexorien == "She" , -9, ifelse(data$sexorien == "Single", -9, ifelse(data$sexorien == "\"Female\"", -9, ifelse(data$sexorien == "L", -9, ifelse(data$sexorien == "M", -9, ifelse(data$sexorien == "\"Feminine\"", -9, ifelse(data$sexorien == "Male", -9,data$sexorien))))))))))))))))))))))))))))
sexOrienLevels = as.factor(dataSexOrien)
levels(sexOrienLevels)



dataAge = ifelse(data$age == "\"?\"", -9, ifelse(data$age == "\"50+\"", -9,ifelse(data$age == "\"Old\"", -9, ifelse(data$age == "40 and fabulous",-9,ifelse(data$age == "No Pre", -9, ifelse(data$age == "\"60+\"", -9, ifelse(data$age == "\"2\"", -9, ifelse(data$age == "45+", -9, ifelse(data$age == "over 21", -9, ifelse(data$age == "\"30+\"", -9,ifelse(data$age == "\"Guess\"", -9, ifelse(data$age == "Illegible", -9, ifelse(data$age == "range 22-68", -9, ifelse(data$age == "\"4\"", -9, ifelse(data$age == "\"MYOB\"", -9, ifelse(data$age == "\"40ish\"", -9, ifelse(data$age == "\"Ø\"", -9,data$age )))))))))))))))))


dataEth = ifelse(data$eth == "\"?\"", -9, ifelse(data$eth == "\"Ø\"" , -9, data$eth))
ethLevels = as.factor(dataEth)
levels(ethLevels)
```
Here is where I first recode all possible missing values into a "Missing" code and then delete the -9's which are the missing values I created in the step above.

For example, I believe that "Flank" is actually "Blank", which is one of the codes the Prism students to code missing values.  Therefore, I am recoding the "Flank" code to "Missing".  Let me know what you think about these codes.
```{r}
data1 = cbind(dataGender, dataSexOrien, dataAge, dataEth, data$site)
data1 = ifelse(data1 == "NA", "Missing", ifelse(data1 == -9, NA, ifelse(data1 == "Blank", "Missing", ifelse( data1 == "N/A", "Missing", ifelse(data1 == "Flank", "Missing",ifelse(data1 == "MIssing", "Missing", ifelse(data1 == "[Crossed something out]", "Missing", data1)))))))
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
Here I created a female variable, other gender identity variable (otherGI), and a straight variable.  

For example, I believed that  "\"Female-> like males\"" meant that they were straight and therefore I coded that as a 1 in the straight variable meaning that they would be classified as straight.  Therefore, the reference category is all non-straight sexual orientations.

For the gender variable, I also created a other gender identity variable, which means that male is the reference category for the gender variable.

For sexual orientation, because straight is coded as one, all non-straight sexual orientations are the reference category.

Let me know what you think about these codes.
```{r}
female = ifelse(data1$gender == "\"Female-->sex, androgyne/butch, top/bottom\"", 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "F.", 1, ifelse(data1$gender =="Femal",1, ifelse(data1$gender == "Female", 1, ifelse(data1$gender == "Female (Cisgender)", 1, ifelse(data1$gender == "Female/she", 1, ifelse(data1$gender == "Femele", 1, ifelse(data1$gender == "Lady" , 1, ifelse(data1$gender == "Woman", 1, ifelse(data1$gender == "\"Female--cisgender\"", 1, ifelse(data1$gender == "\"She\"", 1, ifelse(data1$gender == "[Female symbol]" , 1, ifelse(data1$gender == "Cis woman", 1, ifelse(data1$gender == "F", 1, ifelse(data1$gender == "Famel",1, ifelse(data1$gender == "Female (cis)", 1, ifelse(data1$gender == "Female/Woman", 1, ifelse(data1$gender == "She, her, hers Female", 1, ifelse(data1$gender == "woman", 1, ifelse(data1$gender =="Woman (she/her)", 1, ifelse(data1$gender == "female", 1, ifelse(data1$gender == "f", 1, ifelse(data1$gender == "Missing", "Missing", 0)))))))))))))))))))))))))

genderLevels = as.factor(data1$gender)
levels(genderLevels)

otherGI =  ifelse(data$gender == "om", 1,ifelse(data1$gender == "Non-binary", 1, ifelse(data1$gender == "Genderqueer", 1, ifelse(data1$gender == "Non-binary", 1, 0))))

head(otherGI)
sum(otherGI)

sexorienLevels = as.factor(data1$sexorien)
levels(sexorienLevels)

straight = ifelse(data1$sexorien ==  "\"Female-> like males\"" , 1, ifelse(data1$sexorien == "\"Straight?\"", 1, ifelse(data1$sexorien == "[Crossed something out] Straight", 1, ifelse(data1$sexorien == "Herdosexual/Straight" , 1, ifelse(data1$sexorien == "hetero", 1, ifelse(data1$sexorien == "Heterosexual", 1, ifelse(data1$sexorien == "Hetero/Cisgender", 1, ifelse(data1$sexorien == "Male-heterosexual",1, ifelse(data1$sexorien == "Married-Hetero", 1, ifelse(data1$sexorien == "Staight" , 1, ifelse(data1$sexorien == "Straight",1, ifelse(data1$sexorien == "Straight Heterosexual", 1, ifelse(data1$sexorien == "Straight/hetero", 1, ifelse(data1$sexorien == "Strait", 1, ifelse(data1$sexorien == "\"Straight/Ally\"", 1, ifelse(data1$sexorien == "[Crossed out \"Stright\"] Stright", 1, ifelse(data1$sexorien == "heter-", 1, ifelse(data1$sexorien == "hetero ", 1, ifelse(data1$sexorien == "Male/Female Traditional Choice", 1, ifelse(data1$sexorien == "s", 1, ifelse(data1$sexorien =="Straght", 1, ifelse(data1$sexorien == "straight " , 1, ifelse(data1$sexorien == "Straight married", 1, ifelse(data1$sexorien == "Straight/Heterosexual", 1, ifelse(data1$sexorien == "streight", 1, ifelse(data1$sexorien == "Hetero/Cisgender" ,1, ifelse(data1$sexorien == "married straight cisender", 1, ifelse(data1$sexorien == "S", 1, ifelse(data1$sexorien =="straight" , 1, ifelse(data1$sexorien == "Straight (Cisgender)", 1, ifelse(data1$sexorien == "Straight.", 1, ifelse(data1$sexorien == "strait", 1, ifelse(data1$sexorien == "Traditional", 1, ifelse(data1$sexorien == "\"F Hetero\"", 1, ifelse(data1$sexorien =="\"Hetero-Female\"", 1, ifelse(data1$sexorien == "\"Straight/ally\"" , 1, ifelse(data1$sexorien == "[Crossed out \"Femal\"] Heterosexual", 1, ifelse(data1$sexorien == "Heteroflexible", 1, ifelse(data1$sexorien == "heterosexual [crossed out straight]", 1, ifelse(data1$sexorien == "Male-heterosexual", 1, ifelse(data1$sexorien == "Straight Heterosexual" , 1, ifelse( data1$sexorien == "Missing", "Missing", 0))))))))))))))))))))))))))))))))))))))))))
```
Now I am doing the same for the ethnicity variable and creating the following categories: black, hispanic, multi (i.e. multiracial), and other ethnicity (otherEth).  Therefore, white is the reference category.
```{r}
ethLevels = as.factor(data1$eth)
levels(ethLevels)

black = ifelse(data1$eth == "Af. Am.", 1, ifelse(data1$eth == "African American", 1, ifelse(data$eth == "African-American", 1, ifelse(data1$eth == "Africian American", 1, ifelse(data1$eth == "black", 1, ifelse(data1$eth == "Black - African American", 1, ifelse(data1$eth == "Black/African American", 1, ifelse(data1$eth == "AA", 1, ifelse(data1$eth ==  "African American Black" , 1, ifelse(data1$eth == "Blacc", 1, ifelse(data1$eth == "Black", 1, ifelse(data1$eth == "Missing", "Missing",0))))))))))))

hispanic =  ifelse(data1$eth ==   "hispanic", 1, ifelse(data1$eth == "H", 1, ifelse(data1$eth == "Hispanic" , 1, ifelse(data1$eth == "Hispanic/Latina", 1, ifelse(data1$eth == "Latina", 1, ifelse(data1$eth == "Latino/Hispanic", 1, ifelse(data1$eth == "Latino", 1, 0)))))))                                                 

multi = ifelse(data1$eth == "hispanic/white", 1, ifelse(data1$eth == "many", 1, ifelse(data1$eth == "Mixed", 1, ifelse(data1$eth == "White & Latinx", 1, ifelse(data1$eth == "\"M\"" , 1, ifelse(data1$eth ==  "African, Irish, American", 1, ifelse(data1$eth == "black + other", 1, ifelse(data1$eth == "Caucasian/Hispanic", 1, ifelse(data1$eth == "m", 1, ifelse(data1$eth == "Many",1, ifelse(data1$eth == "Mix", 1, ifelse(data1$eth == "Mixed white/South Asian", 1, ifelse(data1$eth == "Multiethnic Afrolatina + white", 1, ifelse(data1$eth == "Multiracial" , 1, ifelse(data1$eth ==  "White/mixed", 1,0))))))))))))))) 

otherEth = ifelse(data1$eth == "\"Indian\"", 1, ifelse(data1$eth == "Asian", 1, ifelse(data1$eth == "\"Greek\"", 1, ifelse(data1$eth == "ai", 1, ifelse(data1$eth == "Native American", 1, ifelse(data1$eth == "None", 1, ifelse(data1$eth == "Asian Pacific Islander", 1, ifelse(data1$eth == "Filipino", 1, ifelse(data1$eth == "Other",1, 0)))))))))
```
Here I am creating a missing data identifier for the sexual orientation variable "sexorien".  I have to create a unique missing variable for each variable separately, because missing data must be deleted from the model.  

For example, if I wanted to assess whether missing data across all variables is related to any of the included variables, I would create a missing variable that is a 1 anytime any variable has a missing value and zero otherwise.  However, because I need to delete all missing values before I run the analysis, I would end up deleting all the 1's in the missing data variable so there would be no variation.

Therefore, if I create a missing variable indicator for one variable (in the example below I create a missing data variable for sex orientation = sexorien), then delete the missing values for the other variables (female, otherGI, black, hispanic, multi, otherEth, age) I can delete the missing values for all other variables and keep missing values for sex orientation that are not also missing for other variables.

For example, if one person had a missing value for both sexual orientation and gender, then using this process they would be deleted from the dataset.

One way either around or to validate this procedure would be to impute missing values.  For example, before imputation, I would create either a binary or count variable representing either each time or the count of missing values across each person for each variable.  Then we can impute the missing values using an R package.  Then we can run the analysis with the binary or count variable indicator that was created before imputation as the dependent variable with all other variables (e.g. female, black) as independent variables.  This has drawbacks as well, because this procedure is assuming that data is missing, because of included variables, but it could be the case that data are missing because of other variables, so it is unclear if the imputed values are any good.  
```{r}
missingSexOrien = data1$sexorien
missingSexOrien = ifelse(data1$sexorien == "Missing", 1, 0)
dataAnalysis = cbind(missingSexOrien, female, otherGI, black, hispanic, multi, otherEth, age = data1$age, site)

dataAnalysis = as.data.frame(dataAnalysis)
head(dataAnalysis)
dataAnalysis = apply(dataAnalysis, 2, function(x){ifelse(x == "Missing", NA, x)})
dataAnalysis = as.data.frame(dataAnalysis)
head(dataAnalysis)
dataAnalysis = na.omit(dataAnalysis)
dataAnalysis = as.data.frame(dataAnalysis)
dim(dataAnalysis)
head(dataAnalysis)
```
Here I have an example of the model with missing values found in the sexual orientation variable indicated as a 1 for missing and 0 for non-missing.  Then I include the other covariates in the model and allow the model to have different intercepts for different sites, which are the locations that each program took place at.

Overall, none of the included covariates are statistically significantly related to missing values in sexual orientation.
```{r}
library(nlme)
library(lme4)
model = glmer(missingSexOrien ~ female + otherGI + black + hispanic + multi + otherEth +(1 | site), family = binomial("logit"), data = dataAnalysis)
summary(model)
```





