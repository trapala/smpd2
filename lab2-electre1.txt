library("MCDA")
library("OutrankingTools")

#install.packages("OutrankingTools")

performanceMatrix <- cbind(
  c(50,55,43,55,43,50,43,49,55,55),
  c(300,450,350,450,275,350,250,350,450,500),
  c(4,7,4,5,6,7,8,9,7,5),
  c(1499,2599,1399,2599,1190,2299,1849,1849,3999,2999))
  
## Vector containing names of alternatives
alternatives <-c("Hitachi50HB5W62","SamsungUE55MU6172","LG43LJ594V","LG55UJ6517","Philips43PFT4112/12","SamsungUE50MU6172","SamsungUE43MU6172","LG49UJ634V","SamsungUE55MU7042","Sony KD-55XE7005")

## Vector containing names of criteria
criteria <-c("Matryca","JasnoscEkranu","CzasReakcjiMatrycy","Cena")

## vector indicating the direction of the criteria evaluation .
minmaxcriteria <-c("max","max","min","min")
## criteriaWeights vector
criteriaWeights <- c(0.3,0.1,0.3,0.2)
x<-Electre_1(performanceMatrix,
             alternatives,
             criteria,
             criteriaWeights,
             minmaxcriteria,
             concordance_threshold=0.8,discordance_threshold=0.1)
print(x)