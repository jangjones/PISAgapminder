# PISAgapminder
Gapminder-style presentation of OECD PISA data using GoogleVis

library(googleVis)
library(devtools)
install_github("mages/googleVis")

PISAdata <- read.csv("https://github.com/jangjones/PISAgapminder/blob/master/AllPISA.csv", 
  header = TRUE,
  quote="\"",
  stringsAsFactors= TRUE,
  strip.white = TRUE)
  
str(PISAdata)
head(PISAdata)

chart<- gvisMotionChart(PISAdata, idvar="Cntry",
  timevar="Time",
  colorvar ="Region",
  xvar = "Year",
  yvar = "MathMean",
  sizevar="Population",
  chartid="PISAdata1")
  
str(chart)
plot(chart)
