---
title       : Mortality in Barcelona
subtitle    : Course Project 
author      : Pere Llimona
job         : Course Project for Developing Data Products MOOC Coursera
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap,quiz]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

Displaying the Mortality in Barcelona using an Excel dataset containing data from Mortality in Barcelona from years 2001 to 2011  (6589 rows), perform a visualization of data from two perspectives: 

1. Evolution of mortality in Barcelona showing all years, according to District and Sex values selected in the sidebar panel combo boxes.
2. Mortality in Barcelona per Cause of death, according to Year, District and Sex selected values in the sidebar panel combo boxes.
3. Calculate and visualize the of mean Comparative Mortality Ratio for each Cause of Death:

```
## Loading required package: XLConnect
## XLConnect 0.2-7 by Mirai Solutions GmbH
## http://www.mirai-solutions.com ,
## http://miraisolutions.wordpress.com
```

```r
#Calculation of mean of Comparative Mortality Ratio
meanrmc <-mean(myset$RMC, na.rm = TRUE)
```

---

## Histogram of Comparative Mortality Ratio

CMR Cause of Death when selected values Year:2011, District:Ciutat Vella, Sex:Both
![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 

---

## Evolution of Mortality in Barcelona (Panel 1)

The Graph displays the evolution of standardized rates per year in Barcelona starting from year 2001 to 2011, and according to the selected District and Sex on the sidebar panel combo boxes.
The Table shows per each year (rows), the following data from Barcelona, according to the selected District and Sex on the sidebar panel combo boxes; by columns:

1. The given year (YEAR) 
2. Number of deaths by age group: from 0 to 14 years old (N01_14), from 15 to 44 (N15_44), from 45 to 74 (N45_44), more than 75 years old (N75_XX), and from all ages (TOTAL)
3. Rate of number of deaths within the amount of population in Barcelona, corresponding to the same age groups (TX01_14,TX15_44,TX45_74,TX75_XX,TXTOTAL)
4. Confidence Interval (IC95)
5. Comparative Mortality Ratio (RMC)
6. Standardized mortality rate balanced with the population of Barcelona in the year 1996 (TSTDTOTAL)

---

## Cause of Death (Panel 2)

The Graph displays an histogram or frequency distribution of values for Comparative Mortality Ratio (RMC), in Barcelona, according to the selected Year, District and Sex on the sidebar panel combo boxes. It also depicts in a red line the mean value for Comparative Mortality Ratio.

The Table shows pear each main Cause of Death Group (17 groups and TOTAL in rows), the following data from Barcelona, according to the selected Year, District and Sex on the sidebar panel combo boxes; by columns:

1. The given Cause of Death(CauseOfDeath) 
2. Confidence Interval (IC95)
3. Comparative Mortality Ratio (RMC)
4. Percent of number of deaths within the Cause of death (PCTTOTAL)
5. Rate of number of deaths within the amount of population in Barcelona (TXOTAL)
6. Standardized mortality rate balanced with the population of Barcelona in the year 1996 (TSTDTOTAL) 

---

## Appendix: The Data Set

Data organized according to the following columns:

1. Years from 2001 to 2011 (Year)
2. The given Cause of Death (CauseOfDeath) 
3. Number of deaths by age group: from 0 to 14 years old (N01_14), from 15 to 44 (N15_44), from 45 to 74 (N45_44), more than 75 years old (N75_XX), and from all ages (TOTAL)
4. Rate of number of deaths within the amount of population in Barcelona, corresponding to the same age groups (TX01_14, TX15_44, TX45_74, TX75_XX, TXTOTAL)
5. Confidence Interval (IC95)
6. Comparative Mortality Ratio (RMC)
7. Percent of number of deaths within the Cause of death (PCTTOTAL)
8. Standardized mortality rate balanced with the population of Barcelona in the year 1996 (TSTDTOTAL) 

---

## Appendix: Sample of data for the Histogram


```
##                                                    CauseOfDeath   RMC
## 6031                       I. Infectious and parasitic diseases 149.5
## 6032                                                II. Tumours 115.4
## 6033           III. Blood's and hematopoietics organ's diseases  46.6
## 6034                        IV. Endocrine/nutritional disorders  95.8
## 6035                              V. Neuropsychiatric disorders 127.1
## 6036             VI. Nervous system's and sense organs diseases  92.1
## 6037                           VII. Circulatory System Diseases 113.1
## 6038                                 VIII. Respiratory diseases 185.0
## 6039                                     IX. Digestive diseases 133.8
## 6040                X. Skin's and subcutaneous tissues diseases 261.2
## 6041      XI. Musculoskeletal's and connective tissues diseases 181.7
## 6042                  XII. Diseases of the genitourinary system 148.3
## 6043          XIII. Complicacions de l'embaràs, part i puerperi    NA
## 6044     XIV. Some illnesses originated in the perinatal period 134.6
## 6045 XV. Congenital malformations and chromosomal abnormalities 213.1
## 6046        XVI. Symptoms, signs and affections wrongly defined 158.8
## 6047                        XVII. External causes of mortalitat 105.1
## 6048                                                      TOTAL 122.7
```
