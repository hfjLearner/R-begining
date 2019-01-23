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
