# R-begining
R language's graph code
#scatter plot
library(ggplot2)
qplot(mtcars$wt,mtcars$mpg)#equivalent to qplot(wt,mpg,data=mtcars)

#line graph
plot(pressure$temperature,pressure$pressure,type='l')
#if you want to add points or add another line to the graph
plot(pressure$temperature,pressure$pressure,type='l')
points(pressure$temperature,pressure$pressure)#add points on the line
lines(pressure$temperature,pressure$pressure/2,col="red")#add another line into the graph frame
points(pressure$temperature,pressure$pressure/2,col="red")#and add points on the second line
#use ggplot2
library(ggplot2)
qplot(pressure$temperature,pressure$pressure,geom="line")#only line;another type qplot(temperature,pressure,data=pressure,geom="line")
qplot(pressure,aes(x=temperature,y=pressure)) + geom_line()#this is equivalent to the above two
qplot(temperature,presssure,data=pressure,geom=c("line","point"))#line and point together

#Bar graph
library(ggplot2)
data <-data.frame(Cultivar=rep(c('c39','c52'),c(3,3)),Date=c('d16','d20','d21','d16','d20','d21'),Weight=c(3.18,2.80,2.74,2.26,3.11,1.47))
qplot(data,aes(x=Date,y=Weight),fill=Cultivar) + geom_bar(position="dodge",stat="identity")
#dodge--避开，为了让柱状分开不堆叠，fill是填充颜色的意思，为了改变柱状图边框颜色使用colour=" "
#ggplot(data,aes(x=Date,y=factor(Weight),fill=Cultivar)) + geom_bar(position="dodge",stat="identity",colour='grey')
