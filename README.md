# foehnix
# Bachelorthesis in meteorology of the university Innsbruck
# ---------------------------------------------
# Name:        Einlesen.R
# Author:      Wieser Hannes
# Date:        2020-02-23
# Description: Small script to read in the data and prepare for foehnix.
# ---------------------------------------------
# Import data

taw_11149 <- read.table("tawes_11149.txt", header = TRUE, sep = "") # Bergstation Salzburg 1772 m
taw_11215 <- read.table("tawes_11215.txt", header = TRUE, sep = "") # 
taw_11260 <- read.table("tawes_11260.txt", header = TRUE, sep = "") # Bergstation Kärnten 1200m
taw_11261 <- read.table("tawes_11261.txt", header = TRUE, sep = "") # 
taw_11262 <- read.table("tawes_11262.txt", header = TRUE, sep = "") # Talstation Kärnten 688 m
taw_11272 <- read.table("tawes_11272.txt", header = TRUE, sep = "") # Obertauern
taw_11348 <- read.table("tawes_11348.txt", header = TRUE, sep = "") # Obertauern
taw_11399 <- read.table("tawes_11399.txt", header = TRUE, sep = "") # Obertauern

any(taw_11149$dd > 360)
taw_11149$dd[taw_11149$dd<360]
# ab <- sort(d$p, decreasing = TRUE)
val <- taw_11149$datumsec 
ab <- as.POSIXct(val, tz = "Europe/Berlin", origin = "1970-01-01")
ab <- as.Date(as.POSIXct(val, tz = "Europe/Berlin", origin = "1970-01-01"))
head(ab)

library(lubridate)
ab <- as_datetime(taw_11149$datumsec)
plot(ab,taw_11149$p)

library(remotes)
C:\Users\hanne\AppData\Local\Temp\RtmpGiYwBj\downloaded_packages
