# Initial-Practice-work-

flagdata_naivebayes_.R
SACHIN

Thu Apr 06 21:36:28 2017

flag.data <- read.csv("D:/stuff/study material/Machine Learning/flag data.csv")
head(flag.data)
##             name landmass zone area population language religion bars
## 1    Afghanistan        5    1  648         16       10        2    0
## 2        Albania        3    1   29          3        6        6    0
## 3        Algeria        4    1 2388         20        8        2    2
## 4 American-Samoa        6    3    0          0        1        1    0
## 5        Andorra        3    1    0          0        6        0    3
## 6         Angola        4    2 1247          7       10        5    0
##   stripes colours red green blue gold while. black orange mainhue circles
## 1       3       5   1     1    0    1      1     1      0   green       0
## 2       0       3   1     0    0    1      0     1      0     red       0
## 3       0       3   1     1    0    0      1     0      0   green       0
## 4       0       5   1     0    1    1      1     0      1    blue       0
## 5       0       3   1     0    1    1      0     0      0    gold       0
## 6       2       3   1     0    0    1      0     1      0     red       0
##   crooses saltires quarters sunstras crescent triangle icon animate text
## 1       0        0        0        1        0        0    1       0    0
## 2       0        0        0        1        0        0    0       1    0
## 3       0        0        0        1        1        0    0       0    0
## 4       0        0        0        0        0        1    1       1    0
## 5       0        0        0        0        0        0    0       0    0
## 6       0        0        0        1        0        0    1       0    0
##   topleft botrigt
## 1   black   green
## 2     red     red
## 3   green   white
## 4    blue     red
## 5    blue     red
## 6     red   black
colnames(flag.data)
##  [1] "name"       "landmass"   "zone"       "area"       "population"
##  [6] "language"   "religion"   "bars"       "stripes"    "colours"   
## [11] "red"        "green"      "blue"       "gold"       "while."    
## [16] "black"      "orange"     "mainhue"    "circles"    "crooses"   
## [21] "saltires"   "quarters"   "sunstras"   "crescent"   "triangle"  
## [26] "icon"       "animate"    "text"       "topleft"    "botrigt"
landmass <- c()
landmass[which(flag.data$landmass  == 1)]  <- "N.America"
landmass[which(flag.data$landmass  == 2)]  <- "S.America"
landmass[which(flag.data$landmass  == 3)]  <- "Europe"
landmass[which(flag.data$landmass  == 4)]  <- "Africa"
landmass[which(flag.data$landmass  == 5)]  <- "Asia"
landmass[which(flag.data$landmass  == 6)]  <- "Oceania"
flag.data $landmass <- as.factor(landmass)

zone  <-  c()
zone[which(flag.data$zone  == 1)]  <- "NE"
zone[which(flag.data$zone  == 2)]  <- "SE"
zone[which(flag.data$zone  == 3)]  <- "SW"
zone[which(flag.data$zone  == 4)]  <- "NW"
flag.data$zone <- as.factor(zone)

language  <- c()
language[which(flag.data$language  == 1)]  <- "English"
language[which(flag.data$language  == 2)]  <- "Spanish"
language[which(flag.data$language  == 3)]  <- "French"
language[which(flag.data$language  == 4)]  <- "German"
language[which(flag.data$language  == 5)]  <- "Slavic"
language[which(flag.data$language  == 6)]  <- "Other IE"
language[which(flag.data$language  == 7)]  <- "Chinese"
language[which(flag.data$language  == 8)]  <- "Arabic"
language[which(flag.data$language  == 9)]  <- "Japanese/Turkish/Finnish/Magyar"
language[which(flag.data$language  == 10)]  <- "Others"
flag.data$language  <- as.factor(language)


religion <- c()
religion[which(flag.data$religion  == 0)]  <- "Catholic"
religion[which(flag.data$religion  == 1)]  <- "Other Christian"
religion[which(flag.data$religion  == 2)]  <- "Muslim"
religion[which(flag.data$religion  == 3)]  <- "Buddhist"
religion[which(flag.data$religion  == 4)]  <- "Hindu"
religion[which(flag.data$religion  == 5)]  <- "Ethnic"
religion[which(flag.data$religion  == 6)]  <- "Marxist"
religion[which(flag.data$religion  == 7)]  <- "Other"
flag.data$religion  <- as.factor(religion)
summary(flag.data)
##              name          landmass  zone         area        
##  Afghanistan   :  1   Africa   :52   NE:91   Min.   :    0.0  
##  Albania       :  1   Asia     :39   NW:58   1st Qu.:    9.0  
##  Algeria       :  1   Europe   :35   SE:29   Median :  111.0  
##  American-Samoa:  1   N.America:31   SW:16   Mean   :  700.0  
##  Andorra       :  1   Oceania  :20           3rd Qu.:  471.2  
##  Angola        :  1   S.America:17           Max.   :22402.0  
##  (Other)       :188                                           
##    population          language             religion       bars       
##  Min.   :   0.00   Others  :46   Other Christian:60   Min.   :0.0000  
##  1st Qu.:   0.00   English :43   Catholic       :40   1st Qu.:0.0000  
##  Median :   4.00   Other IE:30   Muslim         :36   Median :0.0000  
##  Mean   :  23.27   Spanish :21   Ethnic         :27   Mean   :0.4536  
##  3rd Qu.:  14.00   Arabic  :19   Marxist        :15   3rd Qu.:0.0000  
##  Max.   :1008.00   French  :17   Buddhist       : 8   Max.   :5.0000  
##                    (Other) :18   (Other)        : 8                   
##     stripes          colours           red             green       
##  Min.   : 0.000   Min.   :1.000   Min.   :0.0000   Min.   :0.0000  
##  1st Qu.: 0.000   1st Qu.:3.000   1st Qu.:1.0000   1st Qu.:0.0000  
##  Median : 0.000   Median :3.000   Median :1.0000   Median :0.0000  
##  Mean   : 1.552   Mean   :3.464   Mean   :0.7887   Mean   :0.4691  
##  3rd Qu.: 3.000   3rd Qu.:4.000   3rd Qu.:1.0000   3rd Qu.:1.0000  
##  Max.   :14.000   Max.   :8.000   Max.   :1.0000   Max.   :1.0000  
##                                                                    
##       blue             gold            while.           black      
##  Min.   :0.0000   Min.   :0.0000   Min.   :0.0000   Min.   :0.000  
##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:1.0000   1st Qu.:0.000  
##  Median :1.0000   Median :0.0000   Median :1.0000   Median :0.000  
##  Mean   :0.5103   Mean   :0.4691   Mean   :0.7526   Mean   :0.268  
##  3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:1.000  
##  Max.   :1.0000   Max.   :1.0000   Max.   :1.0000   Max.   :1.000  
##                                                                    
##      orange         mainhue      circles          crooses      
##  Min.   :0.000   red    :71   Min.   :0.0000   Min.   :0.0000  
##  1st Qu.:0.000   blue   :40   1st Qu.:0.0000   1st Qu.:0.0000  
##  Median :0.000   green  :31   Median :0.0000   Median :0.0000  
##  Mean   :0.134   white  :22   Mean   :0.1701   Mean   :0.1495  
##  3rd Qu.:0.000   gold   :19   3rd Qu.:0.0000   3rd Qu.:0.0000  
##  Max.   :1.000   black  : 5   Max.   :4.0000   Max.   :2.0000  
##                  (Other): 6                                    
##     saltires          quarters         sunstras         crescent     
##  Min.   :0.00000   Min.   :0.0000   Min.   : 0.000   Min.   :0.0000  
##  1st Qu.:0.00000   1st Qu.:0.0000   1st Qu.: 0.000   1st Qu.:0.0000  
##  Median :0.00000   Median :0.0000   Median : 0.000   Median :0.0000  
##  Mean   :0.09278   Mean   :0.1495   Mean   : 1.387   Mean   :0.0567  
##  3rd Qu.:0.00000   3rd Qu.:0.0000   3rd Qu.: 1.000   3rd Qu.:0.0000  
##  Max.   :1.00000   Max.   :4.0000   Max.   :50.000   Max.   :1.0000  
##                                                                      
##     triangle           icon           animate           text        
##  Min.   :0.0000   Min.   :0.0000   Min.   :0.000   Min.   :0.00000  
##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:0.000   1st Qu.:0.00000  
##  Median :0.0000   Median :0.0000   Median :0.000   Median :0.00000  
##  Mean   :0.1392   Mean   :0.2526   Mean   :0.201   Mean   :0.08247  
##  3rd Qu.:0.0000   3rd Qu.:0.7500   3rd Qu.:0.000   3rd Qu.:0.00000  
##  Max.   :1.0000   Max.   :1.0000   Max.   :1.000   Max.   :1.00000  
##                                                                     
##    topleft      botrigt  
##  black :12   red    :69  
##  blue  :43   blue   :47  
##  gold  : 6   green  :40  
##  green :32   white  :17  
##  orange: 4   black  : 9  
##  red   :56   gold   : 9  
##  white :41   (Other): 3
str(flag.data)
## 'data.frame':    194 obs. of  30 variables:
##  $ name      : Factor w/ 194 levels "Afghanistan",..: 1 2 3 4 5 6 7 8 9 10 ...
##  $ landmass  : Factor w/ 6 levels "Africa","Asia",..: 2 3 1 5 3 1 4 4 6 6 ...
##  $ zone      : Factor w/ 4 levels "NE","NW","SE",..: 1 1 1 4 1 3 2 2 4 4 ...
##  $ area      : int  648 29 2388 0 0 1247 0 0 2777 2777 ...
##  $ population: int  16 3 20 0 0 7 0 0 28 28 ...
##  $ language  : Factor w/ 10 levels "Arabic","Chinese",..: 8 7 1 3 7 8 3 3 10 10 ...
##  $ religion  : Factor w/ 8 levels "Buddhist","Catholic",..: 6 5 6 8 2 3 8 8 2 2 ...
##  $ bars      : int  0 0 2 0 3 0 0 0 0 0 ...
##  $ stripes   : int  3 0 0 0 0 2 1 1 3 3 ...
##  $ colours   : int  5 3 3 5 3 3 3 5 2 3 ...
##  $ red       : int  1 1 1 1 1 1 0 1 0 0 ...
##  $ green     : int  1 0 1 0 0 0 0 0 0 0 ...
##  $ blue      : int  0 0 0 1 1 0 1 1 1 1 ...
##  $ gold      : int  1 1 0 1 1 1 0 1 0 1 ...
##  $ while.    : int  1 0 1 1 0 0 1 1 1 1 ...
##  $ black     : int  1 1 0 0 0 1 0 1 0 0 ...
##  $ orange    : int  0 0 0 1 0 0 1 0 0 0 ...
##  $ mainhue   : Factor w/ 8 levels "black","blue",..: 5 7 5 2 4 7 8 7 2 2 ...
##  $ circles   : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ crooses   : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ saltires  : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ quarters  : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ sunstras  : int  1 1 1 0 0 1 0 1 0 1 ...
##  $ crescent  : int  0 0 1 0 0 0 0 0 0 0 ...
##  $ triangle  : int  0 0 0 1 0 0 0 1 0 0 ...
##  $ icon      : int  1 0 0 1 0 1 0 0 0 0 ...
##  $ animate   : int  0 1 0 1 0 0 1 0 0 0 ...
##  $ text      : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ topleft   : Factor w/ 7 levels "black","blue",..: 1 6 4 2 2 6 7 1 2 2 ...
##  $ botrigt   : Factor w/ 8 levels "black","blue",..: 5 7 8 7 7 1 2 7 2 2 ...
class0 <- subset(flag.data,religion == "Catholic")
class1 <- subset(flag.data,religion == "Other Christian")
class2 <- subset(flag.data,religion == "Muslim")
class3 <- subset(flag.data,religion == "Buddhist")
class4 <- subset(flag.data,religion == "Hindu")
class5 <- subset(flag.data,religion == "Ethnic")
class6 <- subset(flag.data,religion == "Marxist")
class7 <- subset(flag.data,religion == "Other")

s0=sample(nrow(class0),0.8*(nrow(class0)))
s1=sample(nrow(class1),0.8*(nrow(class1)))
s2=sample(nrow(class2),0.8*(nrow(class2)))
s3=sample(nrow(class3),0.8*(nrow(class3)))
s4=sample(nrow(class4),0.8*(nrow(class4)))
s5=sample(nrow(class5),0.8*(nrow(class5)))
s6=sample(nrow(class6),0.8*(nrow(class6)))
s7=sample(nrow(class7),0.8*(nrow(class7)))

train0=class0[s0,]
train1=class1[s1,]
train2=class2[s2,]
train3=class3[s3,]

train4=class4[s4,]
train5=class5[s5,]
train6=class6[s6,]
train7=class7[s7,]

test0=class0[-s0,]
test1=class1[-s1,]
test2=class2[-s2,]
test3=class3[-s3,]
test4=class4[-s4,]
test5=class5[-s5,]
test6=class6[-s6,]
test7=class7[-s7,]

train <- rbind(train0,train1,train2,train3,train4,train5,train6,train7)
test <- rbind(test0,test1,test2,test3,test4,test5,test6,test7)

require(e1071)
## Loading required package: e1071
## Warning: package 'e1071' was built under R version 3.3.2
flag_model <- naiveBayes(religion~.,train,laplace = 1)
flag_model
## 
## Naive Bayes Classifier for Discrete Predictors
## 
## Call:
## naiveBayes.default(x = X, y = Y, laplace = laplace)
## 
## A-priori probabilities:
## Y
##        Buddhist        Catholic          Ethnic           Hindu 
##      0.03921569      0.20915033      0.13725490      0.01960784 
##         Marxist          Muslim           Other Other Christian 
##      0.07843137      0.18300654      0.01960784      0.31372549 
## 
## Conditional probabilities:
##                  name
## Y                 Afghanistan     Albania     Algeria American-Samoa
##   Buddhist        0.005000000 0.005000000 0.005000000    0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779    0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163    0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142    0.005076142
##   Marxist         0.004854369 0.009708738 0.004854369    0.004854369
##   Muslim          0.009009009 0.004504505 0.004504505    0.004504505
##   Other           0.005076142 0.005076142 0.005076142    0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231    0.008264463
##                  name
## Y                     Andorra      Angola    Anguilla Antigua-Barbuda
##   Buddhist        0.005000000 0.005000000 0.005000000     0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779     0.004424779
##   Ethnic          0.004651163 0.009302326 0.004651163     0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142     0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369     0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505     0.004504505
##   Other           0.005076142 0.005076142 0.005076142     0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231     0.008264463
##                  name
## Y                   Argentina   Argentine   Australia     Austria
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.008849558 0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.008264463 0.004132231
##                  name
## Y                     Bahamas     Bahrain  Bangladesh    Barbados
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009 0.009009009 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.008264463 0.004132231 0.004132231 0.004132231
##                  name
## Y                     Belgium      Belize       Benin     Bermuda
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.009302326 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.008264463
##                  name
## Y                      Bhutan     Bolivia    Botswana      Brazil
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.008849558 0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163 0.009302326 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                 British-Virgin-Isles      Brunei    Bulgaria     Burkina
##   Buddhist                 0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic                 0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic                   0.004651163 0.004651163 0.004651163 0.009302326
##   Hindu                    0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist                  0.004854369 0.004854369 0.009708738 0.004854369
##   Muslim                   0.004504505 0.009009009 0.004504505 0.004504505
##   Other                    0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian          0.008264463 0.004132231 0.004132231 0.004132231
##                  name
## Y                       Burma     Burundi    Cameroon      Canada
##   Buddhist        0.010000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.008264463 0.008264463
##                  name
## Y                 Cape-Verde-Islands Cayman-Islands
##   Buddhist               0.005000000    0.005000000
##   Catholic               0.008849558    0.004424779
##   Ethnic                 0.004651163    0.004651163
##   Hindu                  0.005076142    0.005076142
##   Marxist                0.004854369    0.004854369
##   Muslim                 0.004504505    0.004504505
##   Other                  0.005076142    0.005076142
##   Other Christian        0.004132231    0.008264463
##                  name
## Y                 Central-African-Republic        Chad       Chile
##   Buddhist                     0.005000000 0.005000000 0.005000000
##   Catholic                     0.004424779 0.004424779 0.008849558
##   Ethnic                       0.009302326 0.009302326 0.004651163
##   Hindu                        0.005076142 0.005076142 0.005076142
##   Marxist                      0.004854369 0.004854369 0.004854369
##   Muslim                       0.004504505 0.004504505 0.004504505
##   Other                        0.005076142 0.005076142 0.005076142
##   Other Christian              0.004132231 0.004132231 0.004132231
##                  name
## Y                       China    Colombia Comorro-Islands       Congo
##   Buddhist        0.005000000 0.005000000     0.005000000 0.005000000
##   Catholic        0.004424779 0.008849558     0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163     0.004651163 0.009302326
##   Hindu           0.005076142 0.005076142     0.005076142 0.005076142
##   Marxist         0.009708738 0.004854369     0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505     0.004504505 0.004504505
##   Other           0.005076142 0.005076142     0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231     0.004132231 0.004132231
##                  name
## Y                 Cook-Islands  Costa-Rica        Cuba      Cyprus
##   Buddhist         0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic         0.004424779 0.008849558 0.004424779 0.004424779
##   Ethnic           0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu            0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist          0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim           0.004504505 0.004504505 0.004504505 0.004504505
##   Other            0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian  0.008264463 0.004132231 0.004132231 0.008264463
##                  name
## Y                 Czechoslovakia     Denmark    Djibouti    Dominica
##   Buddhist           0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic           0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic             0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu              0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist            0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim             0.004504505 0.004504505 0.009009009 0.004504505
##   Other              0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian    0.004132231 0.004132231 0.004132231 0.008264463
##                  name
## Y                 Dominican-Republic     Ecuador       Egypt El-Salvador
##   Buddhist               0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic               0.008849558 0.008849558 0.004424779 0.004424779
##   Ethnic                 0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu                  0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist                0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim                 0.004504505 0.004504505 0.009009009 0.004504505
##   Other                  0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian        0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                 Equatorial-Guinea    Ethiopia     Faeroes
##   Buddhist              0.005000000 0.005000000 0.005000000
##   Catholic              0.004424779 0.004424779 0.004424779
##   Ethnic                0.009302326 0.004651163 0.004651163
##   Hindu                 0.005076142 0.005076142 0.005076142
##   Marxist               0.004854369 0.004854369 0.004854369
##   Muslim                0.004504505 0.004504505 0.004504505
##   Other                 0.005076142 0.005076142 0.005076142
##   Other Christian       0.004132231 0.008264463 0.008264463
##                  name
## Y                 Falklands-Malvinas        Fiji     Finland      France
##   Buddhist               0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic               0.004424779 0.004424779 0.004424779 0.008849558
##   Ethnic                 0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu                  0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist                0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim                 0.004504505 0.004504505 0.004504505 0.004504505
##   Other                  0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian        0.008264463 0.008264463 0.008264463 0.004132231
##                  name
## Y                 French-Guiana French-Polynesia       Gabon      Gambia
##   Buddhist          0.005000000      0.005000000 0.005000000 0.005000000
##   Catholic          0.004424779      0.004424779 0.004424779 0.004424779
##   Ethnic            0.004651163      0.004651163 0.009302326 0.009302326
##   Hindu             0.005076142      0.005076142 0.005076142 0.005076142
##   Marxist           0.004854369      0.004854369 0.004854369 0.004854369
##   Muslim            0.004504505      0.004504505 0.004504505 0.004504505
##   Other             0.005076142      0.005076142 0.005076142 0.005076142
##   Other Christian   0.004132231      0.004132231 0.004132231 0.004132231
##                  name
## Y                 Germany-DDR Germany-FRG       Ghana   Gibraltar
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.009302326 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.009708738 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                      Greece   Greenland     Grenada        Guam
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.008264463 0.004132231 0.008264463 0.008264463
##                  name
## Y                   Guatemala      Guinea Guinea-Bissau      Guyana
##   Buddhist        0.005000000 0.005000000   0.005000000 0.005000000
##   Catholic        0.008849558 0.004424779   0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163   0.009302326 0.004651163
##   Hindu           0.005076142 0.005076142   0.005076142 0.010152284
##   Marxist         0.004854369 0.004854369   0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009   0.004504505 0.004504505
##   Other           0.005076142 0.005076142   0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231   0.004132231 0.004132231
##                  name
## Y                       Haiti    Honduras   Hong-Kong     Hungary
##   Buddhist        0.005000000 0.005000000 0.010000000 0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.009708738
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                     Iceland       India   Indonesia        Iran
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.010152284 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.009009009 0.009009009
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.008264463 0.004132231 0.004132231 0.004132231
##                  name
## Y                        Iraq     Ireland      Israel       Italy
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.008849558 0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.009009009 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.010152284 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                 Ivory-Coast     Jamaica       Japan      Jordan
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.009302326 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.009009009
##   Other           0.005076142 0.005076142 0.010152284 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                   Kampuchea       Kenya    Kiribati      Kuwait
##   Buddhist        0.010000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.009302326 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.009009009
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.008264463 0.004132231
##                  name
## Y                        Laos     Lebanon     Lesotho     Liberia
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.009302326
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.009708738 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                       Libya Liechtenstein  Luxembourg    Malagasy
##   Buddhist        0.005000000   0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779   0.008849558 0.008849558 0.004424779
##   Ethnic          0.004651163   0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142   0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369   0.004854369 0.004854369 0.004854369
##   Muslim          0.009009009   0.004504505 0.004504505 0.004504505
##   Other           0.005076142   0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231   0.004132231 0.004132231 0.008264463
##                  name
## Y                      Malawi    Malaysia Maldive-Islands        Mali
##   Buddhist        0.005000000 0.005000000     0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779     0.004424779 0.004424779
##   Ethnic          0.009302326 0.004651163     0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142     0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369     0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009     0.009009009 0.009009009
##   Other           0.005076142 0.005076142     0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231     0.004132231 0.004132231
##                  name
## Y                       Malta    Marianas  Mauritania   Mauritius
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.010152284
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.009009009 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                      Mexico  Micronesia      Monaco    Mongolia
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.009708738
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.008264463 0.004132231 0.004132231
##                  name
## Y                  Montserrat     Morocco  Mozambique       Nauru
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.009302326 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.008264463
##                  name
## Y                       Nepal Netherlands Netherlands-Antilles New-Zealand
##   Buddhist        0.005000000 0.005000000          0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779          0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163          0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142          0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369          0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505          0.004504505 0.004504505
##   Other           0.005076142 0.005076142          0.005076142 0.005076142
##   Other Christian 0.004132231 0.008264463          0.008264463 0.008264463
##                  name
## Y                   Nicaragua       Niger     Nigeria        Niue
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.009009009 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.008264463
##                  name
## Y                 North-Korea North-Yemen      Norway        Oman
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.009009009 0.004504505 0.009009009
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.008264463 0.004132231
##                  name
## Y                    Pakistan      Panama Papua-New-Guinea     Parguay
##   Buddhist        0.005000000 0.005000000      0.005000000 0.005000000
##   Catholic        0.004424779 0.008849558      0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163      0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142      0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369      0.004854369 0.004854369
##   Muslim          0.009009009 0.004504505      0.004504505 0.004504505
##   Other           0.005076142 0.005076142      0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231      0.004132231 0.004132231
##                  name
## Y                        Peru Philippines      Poland    Portugal
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.008849558 0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.009708738 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                 Puerto-Rico       Qatar     Romania      Rwanda
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.009708738 0.004854369
##   Muslim          0.004504505 0.009009009 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                  San-Marino    Sao-Tome Saudi-Arabia     Senegal
##   Buddhist        0.005000000 0.005000000  0.005000000 0.005000000
##   Catholic        0.008849558 0.008849558  0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163  0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142  0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369  0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505  0.004504505 0.004504505
##   Other           0.005076142 0.005076142  0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231  0.004132231 0.004132231
##                  name
## Y                  Seychelles Sierra-Leone   Singapore Soloman-Islands
##   Buddhist        0.005000000  0.005000000 0.010000000     0.005000000
##   Catholic        0.004424779  0.004424779 0.004424779     0.004424779
##   Ethnic          0.004651163  0.009302326 0.004651163     0.004651163
##   Hindu           0.005076142  0.005076142 0.005076142     0.005076142
##   Marxist         0.004854369  0.004854369 0.004854369     0.004854369
##   Muslim          0.004504505  0.004504505 0.004504505     0.004504505
##   Other           0.005076142  0.005076142 0.005076142     0.005076142
##   Other Christian 0.008264463  0.004132231 0.004132231     0.008264463
##                  name
## Y                     Somalia South-Africa South-Korea South-Yemen
##   Buddhist        0.005000000  0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779  0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163  0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142  0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369  0.004854369 0.004854369 0.004854369
##   Muslim          0.009009009  0.004504505 0.004504505 0.009009009
##   Other           0.005076142  0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231  0.008264463 0.004132231 0.004132231
##                  name
## Y                       Spain   Sri-Lanka   St-Helena St-Kitts-Nevis
##   Buddhist        0.005000000 0.010000000 0.005000000    0.005000000
##   Catholic        0.008849558 0.004424779 0.004424779    0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163    0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142    0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369    0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505    0.004504505
##   Other           0.005076142 0.005076142 0.005076142    0.005076142
##   Other Christian 0.004132231 0.004132231 0.008264463    0.008264463
##                  name
## Y                    St-Lucia  St-Vincent       Sudan     Surinam
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.008264463 0.004132231 0.004132231 0.008264463
##                  name
## Y                   Swaziland      Sweden Switzerland       Syria
##   Buddhist        0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.009009009
##   Other           0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian 0.008264463 0.008264463 0.008264463 0.004132231
##                  name
## Y                      Taiwan    Tanzania    Thailand        Togo
##   Buddhist        0.010000000 0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163 0.009302326 0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505 0.004504505 0.004504505
##   Other           0.005076142 0.005076142 0.005076142 0.010152284
##   Other Christian 0.004132231 0.004132231 0.004132231 0.004132231
##                  name
## Y                       Tonga Trinidad-Tobago     Tunisia      Turkey
##   Buddhist        0.005000000     0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779     0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163     0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142     0.005076142 0.005076142 0.005076142
##   Marxist         0.004854369     0.004854369 0.004854369 0.004854369
##   Muslim          0.004504505     0.004504505 0.009009009 0.004504505
##   Other           0.005076142     0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231     0.008264463 0.004132231 0.004132231
##                  name
## Y                 Turks-Cocos-Islands      Tuvalu         UAE      Uganda
##   Buddhist                0.005000000 0.005000000 0.005000000 0.005000000
##   Catholic                0.004424779 0.004424779 0.004424779 0.004424779
##   Ethnic                  0.004651163 0.004651163 0.004651163 0.004651163
##   Hindu                   0.005076142 0.005076142 0.005076142 0.005076142
##   Marxist                 0.004854369 0.004854369 0.004854369 0.004854369
##   Muslim                  0.004504505 0.004504505 0.004504505 0.004504505
##   Other                   0.005076142 0.005076142 0.005076142 0.005076142
##   Other Christian         0.008264463 0.008264463 0.004132231 0.004132231
##                  name
## Y                          UK     Uruguay US-Virgin-Isles         USA
##   Buddhist        0.005000000 0.005000000     0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779     0.004424779 0.004424779
##   Ethnic          0.004651163 0.004651163     0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142     0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369     0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505     0.004504505 0.004504505
##   Other           0.005076142 0.005076142     0.005076142 0.005076142
##   Other Christian 0.008264463 0.004132231     0.008264463 0.008264463
##                  name
## Y                        USSR     Vanuatu Vatican-City   Venezuela
##   Buddhist        0.005000000 0.005000000  0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779  0.004424779 0.008849558
##   Ethnic          0.004651163 0.004651163  0.004651163 0.004651163
##   Hindu           0.005076142 0.005076142  0.005076142 0.005076142
##   Marxist         0.009708738 0.004854369  0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505  0.004504505 0.004504505
##   Other           0.005076142 0.005076142  0.005076142 0.005076142
##   Other Christian 0.004132231 0.008264463  0.004132231 0.004132231
##                  name
## Y                     Vietnam Western-Samoa  Yugoslavia       Zaire
##   Buddhist        0.005000000   0.005000000 0.005000000 0.005000000
##   Catholic        0.004424779   0.004424779 0.004424779 0.004424779
##   Ethnic          0.004651163   0.004651163 0.004651163 0.004651163
##   Hindu           0.005076142   0.005076142 0.005076142 0.005076142
##   Marxist         0.009708738   0.004854369 0.009708738 0.004854369
##   Muslim          0.004504505   0.004504505 0.004504505 0.004504505
##   Other           0.005076142   0.005076142 0.005076142 0.005076142
##   Other Christian 0.004132231   0.008264463 0.004132231 0.004132231
##                  name
## Y                      Zambia    Zimbabwe
##   Buddhist        0.005000000 0.005000000
##   Catholic        0.004424779 0.004424779
##   Ethnic          0.009302326 0.009302326
##   Hindu           0.005076142 0.005076142
##   Marxist         0.004854369 0.004854369
##   Muslim          0.004504505 0.004504505
##   Other           0.005076142 0.005076142
##   Other Christian 0.004132231 0.004132231
## 
##                  landmass
## Y                     Africa       Asia     Europe  N.America    Oceania
##   Buddhist        0.08333333 0.58333333 0.08333333 0.08333333 0.08333333
##   Catholic        0.07894737 0.02631579 0.34210526 0.18421053 0.05263158
##   Ethnic          0.81481481 0.03703704 0.03703704 0.03703704 0.03703704
##   Hindu           0.22222222 0.22222222 0.11111111 0.11111111 0.11111111
##   Marxist         0.05555556 0.33333333 0.44444444 0.05555556 0.05555556
##   Muslim          0.32352941 0.52941176 0.02941176 0.02941176 0.05882353
##   Other           0.22222222 0.33333333 0.11111111 0.11111111 0.11111111
##   Other Christian 0.14814815 0.01851852 0.20370370 0.27777778 0.27777778
##                  landmass
## Y                  S.America
##   Buddhist        0.08333333
##   Catholic        0.31578947
##   Ethnic          0.03703704
##   Hindu           0.22222222
##   Marxist         0.05555556
##   Muslim          0.02941176
##   Other           0.11111111
##   Other Christian 0.07407407
## 
##                  zone
## Y                         NE         NW         SE         SW
##   Buddhist        0.70000000 0.10000000 0.10000000 0.10000000
##   Catholic        0.33333333 0.38888889 0.02777778 0.25000000
##   Ethnic          0.24000000 0.32000000 0.40000000 0.04000000
##   Hindu           0.28571429 0.28571429 0.28571429 0.14285714
##   Marxist         0.81250000 0.06250000 0.06250000 0.06250000
##   Muslim          0.75000000 0.15625000 0.06250000 0.03125000
##   Other           0.57142857 0.14285714 0.14285714 0.14285714
##   Other Christian 0.25000000 0.38461538 0.23076923 0.13461538
## 
##                  area
## Y                      [,1]      [,2]
##   Buddhist         160.5000  262.1212
##   Catholic         698.0000 1595.2618
##   Ethnic           435.3810  387.8589
##   Hindu           1161.6667 1827.2445
##   Marxist         2937.0833 6692.0367
##   Muslim           514.7143  569.9099
##   Other            150.0000  193.0984
##   Other Christian  680.5625 2203.6454
## 
##                  population
## Y                       [,1]       [,2]
##   Buddhist         13.666667  12.027746
##   Catholic         16.187500  24.839404
##   Ethnic            5.761905   5.412068
##   Hindu           228.666667 394.330234
##   Marxist         122.250000 288.912735
##   Muslim           21.250000  36.221157
##   Other            41.333333  66.402811
##   Other Christian   9.500000  34.319525
## 
##                  language
## Y                     Arabic    Chinese    English     French     German
##   Buddhist        0.06250000 0.25000000 0.06250000 0.06250000 0.06250000
##   Catholic        0.02380952 0.02380952 0.04761905 0.07142857 0.09523810
##   Ethnic          0.03225806 0.03225806 0.12903226 0.16129032 0.03225806
##   Hindu           0.07692308 0.07692308 0.23076923 0.07692308 0.07692308
##   Marxist         0.04545455 0.09090909 0.04545455 0.04545455 0.09090909
##   Muslim          0.42105263 0.02631579 0.02631579 0.10526316 0.02631579
##   Other           0.07692308 0.07692308 0.07692308 0.15384615 0.07692308
##   Other Christian 0.01724138 0.01724138 0.51724138 0.03448276 0.03448276
##                  language
## Y                 Japanese/Turkish/Finnish/Magyar   Other IE     Others
##   Buddhist                             0.06250000 0.06250000 0.25000000
##   Catholic                             0.02380952 0.21428571 0.07142857
##   Ethnic                               0.03225806 0.06451613 0.45161290
##   Hindu                                0.07692308 0.15384615 0.07692308
##   Marxist                              0.09090909 0.18181818 0.18181818
##   Muslim                               0.02631579 0.10526316 0.21052632
##   Other                                0.15384615 0.07692308 0.15384615
##   Other Christian                      0.03448276 0.20689655 0.10344828
##                  language
## Y                     Slavic    Spanish
##   Buddhist        0.06250000 0.06250000
##   Catholic        0.02380952 0.40476190
##   Ethnic          0.03225806 0.03225806
##   Hindu           0.07692308 0.07692308
##   Marxist         0.18181818 0.04545455
##   Muslim          0.02631579 0.02631579
##   Other           0.07692308 0.07692308
##   Other Christian 0.01724138 0.01724138
## 
##                  bars
## Y                      [,1]      [,2]
##   Buddhist        0.3333333 0.8164966
##   Catholic        0.8125000 1.2810656
##   Ethnic          0.5238095 1.0779169
##   Hindu           0.0000000 0.0000000
##   Marxist         0.5000000 1.1677484
##   Muslim          0.3571429 0.9511897
##   Other           0.0000000 0.0000000
##   Other Christian 0.1250000 0.5309566
## 
##                  stripes
## Y                      [,1]      [,2]
##   Buddhist        0.3333333 0.8164966
##   Catholic        1.6875000 1.6350496
##   Ethnic          2.8095238 2.8393494
##   Hindu           2.3333333 2.0816660
##   Marxist         1.4166667 1.5050420
##   Muslim          1.6785714 2.7895781
##   Other           2.3333333 2.5166115
##   Other Christian 1.0625000 2.5129981
## 
##                  colours
## Y                     [,1]      [,2]
##   Buddhist        3.333333 1.5055453
##   Catholic        3.187500 1.1760376
##   Ethnic          3.571429 0.8106435
##   Hindu           4.333333 0.5773503
##   Marxist         3.250000 1.4847712
##   Muslim          3.035714 1.0357371
##   Other           2.666667 1.1547005
##   Other Christian 4.000000 1.5436900
## 
##                  red
## Y                      [,1]      [,2]
##   Buddhist        0.8333333 0.4082483
##   Catholic        0.7812500 0.4200134
##   Ethnic          0.8095238 0.4023739
##   Hindu           0.6666667 0.5773503
##   Marxist         1.0000000 0.0000000
##   Muslim          0.7857143 0.4178554
##   Other           0.6666667 0.5773503
##   Other Christian 0.8125000 0.3944428
## 
##                  green
## Y                      [,1]      [,2]
##   Buddhist        0.3333333 0.5163978
##   Catholic        0.2812500 0.4568034
##   Ethnic          0.8095238 0.4023739
##   Hindu           1.0000000 0.0000000
##   Marxist         0.2500000 0.4522670
##   Muslim          0.6785714 0.4755949
##   Other           0.3333333 0.5773503
##   Other Christian 0.4375000 0.5013280
## 
##                  blue
## Y                      [,1]      [,2]
##   Buddhist        0.5000000 0.5477226
##   Catholic        0.6562500 0.4825587
##   Ethnic          0.4285714 0.5070926
##   Hindu           0.6666667 0.5773503
##   Marxist         0.4166667 0.5149287
##   Muslim          0.1428571 0.3563483
##   Other           0.3333333 0.5773503
##   Other Christian 0.7500000 0.4375950
## 
##                  gold
## Y                      [,1]      [,2]
##   Buddhist        0.5000000 0.5477226
##   Catholic        0.4687500 0.5070073
##   Ethnic          0.5238095 0.5117663
##   Hindu           0.6666667 0.5773503
##   Marxist         0.7500000 0.4522670
##   Muslim          0.2500000 0.4409586
##   Other           0.3333333 0.5773503
##   Other Christian 0.5833333 0.4982238
## 
##                  while.
## Y                      [,1]      [,2]
##   Buddhist        0.6666667 0.5163978
##   Catholic        0.6875000 0.4709291
##   Ethnic          0.4761905 0.5117663
##   Hindu           0.6666667 0.5773503
##   Marxist         0.5000000 0.5222330
##   Muslim          0.7857143 0.4178554
##   Other           1.0000000 0.0000000
##   Other Christian 0.8750000 0.3342187
## 
##                  black
## Y                      [,1]      [,2]
##   Buddhist        0.0000000 0.0000000
##   Catholic        0.2187500 0.4200134
##   Ethnic          0.4761905 0.5117663
##   Hindu           0.3333333 0.5773503
##   Marxist         0.1666667 0.3892495
##   Muslim          0.3214286 0.4755949
##   Other           0.0000000 0.0000000
##   Other Christian 0.1875000 0.3944428
## 
##                  orange
## Y                       [,1]      [,2]
##   Buddhist        0.33333333 0.5163978
##   Catholic        0.09375000 0.2961446
##   Ethnic          0.04761905 0.2182179
##   Hindu           0.33333333 0.5773503
##   Marxist         0.08333333 0.2886751
##   Muslim          0.07142857 0.2622653
##   Other           0.00000000 0.0000000
##   Other Christian 0.18750000 0.3944428
## 
##                  mainhue
## Y                      black       blue      brown       gold      green
##   Buddhist        0.07142857 0.14285714 0.07142857 0.14285714 0.07142857
##   Catholic        0.05000000 0.20000000 0.02500000 0.15000000 0.07500000
##   Ethnic          0.03448276 0.06896552 0.03448276 0.17241379 0.27586207
##   Hindu           0.09090909 0.09090909 0.09090909 0.09090909 0.18181818
##   Marxist         0.05000000 0.05000000 0.05000000 0.10000000 0.05000000
##   Muslim          0.08333333 0.08333333 0.05555556 0.11111111 0.22222222
##   Other           0.09090909 0.09090909 0.09090909 0.09090909 0.18181818
##   Other Christian 0.01785714 0.37500000 0.01785714 0.07142857 0.08928571
##                  mainhue
## Y                     orange        red      white
##   Buddhist        0.07142857 0.28571429 0.14285714
##   Catholic        0.02500000 0.35000000 0.12500000
##   Ethnic          0.03448276 0.31034483 0.06896552
##   Hindu           0.18181818 0.18181818 0.09090909
##   Marxist         0.05000000 0.55000000 0.10000000
##   Muslim          0.02777778 0.38888889 0.02777778
##   Other           0.09090909 0.09090909 0.27272727
##   Other Christian 0.03571429 0.26785714 0.12500000
## 
##                  circles
## Y                       [,1]      [,2]
##   Buddhist        0.33333333 0.5163978
##   Catholic        0.09375000 0.2961446
##   Ethnic          0.04761905 0.2182179
##   Hindu           0.33333333 0.5773503
##   Marxist         0.25000000 0.6215816
##   Muslim          0.07142857 0.2622653
##   Other           0.33333333 0.5773503
##   Other Christian 0.14583333 0.3566740
## 
##                  crooses
## Y                      [,1]      [,2]
##   Buddhist        0.1666667 0.4082483
##   Catholic        0.0625000 0.2459347
##   Ethnic          0.0000000 0.0000000
##   Hindu           0.0000000 0.0000000
##   Marxist         0.0000000 0.0000000
##   Muslim          0.0000000 0.0000000
##   Other           0.0000000 0.0000000
##   Other Christian 0.4583333 0.5441501
## 
##                  saltires
## Y                      [,1]      [,2]
##   Buddhist        0.1666667 0.4082483
##   Catholic        0.0000000 0.0000000
##   Ethnic          0.0000000 0.0000000
##   Hindu           0.0000000 0.0000000
##   Marxist         0.0000000 0.0000000
##   Muslim          0.0000000 0.0000000
##   Other           0.0000000 0.0000000
##   Other Christian 0.2916667 0.4593396
## 
##                  quarters
## Y                       [,1]      [,2]
##   Buddhist        0.50000000 0.5477226
##   Catholic        0.15625000 0.7233156
##   Ethnic          0.04761905 0.2182179
##   Hindu           0.00000000 0.0000000
##   Marxist         0.00000000 0.0000000
##   Muslim          0.03571429 0.1889822
##   Other           0.33333333 0.5773503
##   Other Christian 0.31250000 0.4684174
## 
##                  sunstras
## Y                      [,1]      [,2]
##   Buddhist        3.3333333 5.5737480
##   Catholic        1.3125000 4.0436130
##   Ethnic          0.5238095 0.5117663
##   Hindu           0.0000000 0.0000000
##   Marxist         1.0833333 1.3789544
##   Muslim          0.5714286 0.7417982
##   Other           1.0000000 0.0000000
##   Other Christian 2.8541667 7.6741888
## 
##                  crescent
## Y                       [,1]      [,2]
##   Buddhist        0.16666667 0.4082483
##   Catholic        0.00000000 0.0000000
##   Ethnic          0.00000000 0.0000000
##   Hindu           0.00000000 0.0000000
##   Marxist         0.08333333 0.2886751
##   Muslim          0.17857143 0.3900210
##   Other           0.00000000 0.0000000
##   Other Christian 0.00000000 0.0000000
## 
##                  triangle
## Y                       [,1]      [,2]
##   Buddhist        0.00000000 0.0000000
##   Catholic        0.09375000 0.2961446
##   Ethnic          0.19047619 0.4023739
##   Hindu           0.33333333 0.5773503
##   Marxist         0.08333333 0.2886751
##   Muslim          0.14285714 0.3563483
##   Other           0.00000000 0.0000000
##   Other Christian 0.18750000 0.3944428
## 
##                  icon
## Y                      [,1]      [,2]
##   Buddhist        0.6666667 0.5163978
##   Catholic        0.1562500 0.3689020
##   Ethnic          0.2380952 0.4364358
##   Hindu           0.3333333 0.5773503
##   Marxist         0.4166667 0.5149287
##   Muslim          0.1428571 0.3563483
##   Other           0.0000000 0.0000000
##   Other Christian 0.2708333 0.4490929
## 
##                  animate
## Y                      [,1]      [,2]
##   Buddhist        0.5000000 0.5477226
##   Catholic        0.0937500 0.2961446
##   Ethnic          0.1428571 0.3585686
##   Hindu           0.0000000 0.0000000
##   Marxist         0.2500000 0.4522670
##   Muslim          0.1071429 0.3149704
##   Other           0.0000000 0.0000000
##   Other Christian 0.3125000 0.4684174
## 
##                  text
## Y                       [,1]      [,2]
##   Buddhist        0.16666667 0.4082483
##   Catholic        0.06250000 0.2459347
##   Ethnic          0.00000000 0.0000000
##   Hindu           0.00000000 0.0000000
##   Marxist         0.08333333 0.2886751
##   Muslim          0.10714286 0.3149704
##   Other           0.00000000 0.0000000
##   Other Christian 0.10416667 0.3087093
## 
##                  topleft
## Y                      black       blue       gold      green     orange
##   Buddhist        0.07692308 0.23076923 0.15384615 0.07692308 0.07692308
##   Catholic        0.07692308 0.30769231 0.10256410 0.15384615 0.02564103
##   Ethnic          0.10714286 0.17857143 0.03571429 0.32142857 0.03571429
##   Hindu           0.20000000 0.10000000 0.10000000 0.10000000 0.20000000
##   Marxist         0.10526316 0.15789474 0.05263158 0.05263158 0.05263158
##   Muslim          0.08571429 0.08571429 0.02857143 0.22857143 0.02857143
##   Other           0.10000000 0.20000000 0.10000000 0.10000000 0.10000000
##   Other Christian 0.05454545 0.23636364 0.01818182 0.10909091 0.03636364
##                  topleft
## Y                        red      white
##   Buddhist        0.23076923 0.15384615
##   Catholic        0.23076923 0.10256410
##   Ethnic          0.28571429 0.03571429
##   Hindu           0.20000000 0.10000000
##   Marxist         0.42105263 0.15789474
##   Muslim          0.37142857 0.17142857
##   Other           0.20000000 0.20000000
##   Other Christian 0.16363636 0.38181818
## 
##                  botrigt
## Y                      black       blue      brown       gold      green
##   Buddhist        0.07142857 0.14285714 0.07142857 0.14285714 0.07142857
##   Catholic        0.02500000 0.25000000 0.02500000 0.02500000 0.12500000
##   Ethnic          0.06896552 0.17241379 0.06896552 0.10344828 0.34482759
##   Hindu           0.09090909 0.09090909 0.09090909 0.09090909 0.36363636
##   Marxist         0.05000000 0.05000000 0.05000000 0.10000000 0.10000000
##   Muslim          0.16666667 0.05555556 0.05555556 0.05555556 0.30555556
##   Other           0.09090909 0.18181818 0.09090909 0.09090909 0.18181818
##   Other Christian 0.01785714 0.39285714 0.01785714 0.05357143 0.12500000
##                  botrigt
## Y                     orange        red      white
##   Buddhist        0.07142857 0.28571429 0.14285714
##   Catholic        0.05000000 0.45000000 0.05000000
##   Ethnic          0.03448276 0.17241379 0.03448276
##   Hindu           0.09090909 0.09090909 0.09090909
##   Marxist         0.05000000 0.55000000 0.05000000
##   Muslim          0.02777778 0.25000000 0.08333333
##   Other           0.09090909 0.09090909 0.18181818
##   Other Christian 0.01785714 0.25000000 0.12500000
summary(flag_model)
##         Length Class  Mode     
## apriori  8     table  numeric  
## tables  29     -none- list     
## levels   8     -none- character
## call     4     -none- call
prediction <- predict(flag_model,test,type = "class")
prediction
##  [1] Other           Other           Other           Other          
##  [5] Hindu           Other           Other           Hindu          
##  [9] Other           Hindu           Hindu           Other          
## [13] Other           Other           Hindu           Hindu          
## [17] Other           Other Christian Hindu           Other          
## [21] Muslim          Other           Hindu           Hindu          
## [25] Other           Hindu           Other           Hindu          
## [29] Hindu           Other           Other           Other          
## [33] Hindu           Other           Hindu           Other          
## [37] Hindu           Other           Other           Other          
## [41] Other          
## 8 Levels: Buddhist Catholic Ethnic Hindu Marxist Muslim ... Other Christian
require(caret)
## Loading required package: caret
## Warning: package 'caret' was built under R version 3.3.2
## Loading required package: lattice
## Loading required package: ggplot2
## Warning: package 'ggplot2' was built under R version 3.3.2
confusionMatrix(prediction,test$religion)
## Confusion Matrix and Statistics
## 
##                  Reference
## Prediction        Buddhist Catholic Ethnic Hindu Marxist Muslim Other
##   Buddhist               0        0      0     0       0      0     0
##   Catholic               0        0      0     0       0      0     0
##   Ethnic                 0        0      0     0       0      0     0
##   Hindu                  1        2      3     0       0      4     0
##   Marxist                0        0      0     0       0      0     0
##   Muslim                 0        0      0     0       0      1     0
##   Other                  1        6      3     1       3      3     1
##   Other Christian        0        0      0     0       0      0     0
##                  Reference
## Prediction        Other Christian
##   Buddhist                      0
##   Catholic                      0
##   Ethnic                        0
##   Hindu                         5
##   Marxist                       0
##   Muslim                        0
##   Other                         6
##   Other Christian               1
## 
## Overall Statistics
##                                           
##                Accuracy : 0.0732          
##                  95% CI : (0.0154, 0.1992)
##     No Information Rate : 0.2927          
##     P-Value [Acc > NIR] : 0.9999          
##                                           
##                   Kappa : 0.0395          
##  Mcnemar's Test P-Value : NA              
## 
## Statistics by Class:
## 
##                      Class: Buddhist Class: Catholic Class: Ethnic
## Sensitivity                  0.00000          0.0000        0.0000
## Specificity                  1.00000          1.0000        1.0000
## Pos Pred Value                   NaN             NaN           NaN
## Neg Pred Value               0.95122          0.8049        0.8537
## Prevalence                   0.04878          0.1951        0.1463
## Detection Rate               0.00000          0.0000        0.0000
## Detection Prevalence         0.00000          0.0000        0.0000
## Balanced Accuracy            0.50000          0.5000        0.5000
##                      Class: Hindu Class: Marxist Class: Muslim
## Sensitivity               0.00000        0.00000       0.12500
## Specificity               0.62500        1.00000       1.00000
## Pos Pred Value            0.00000            NaN       1.00000
## Neg Pred Value            0.96154        0.92683       0.82500
## Prevalence                0.02439        0.07317       0.19512
## Detection Rate            0.00000        0.00000       0.02439
## Detection Prevalence      0.36585        0.00000       0.02439
## Balanced Accuracy         0.31250        0.50000       0.56250
##                      Class: Other Class: Other Christian
## Sensitivity               1.00000                0.08333
## Specificity               0.42500                1.00000
## Pos Pred Value            0.04167                1.00000
## Neg Pred Value            1.00000                0.72500
## Prevalence                0.02439                0.29268
## Detection Rate            0.02439                0.02439
## Detection Prevalence      0.58537                0.02439
## Balanced Accuracy         0.71250                0.54167
