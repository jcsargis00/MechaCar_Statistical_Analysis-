# MechaCar_Statistical_Analysis
## Linear Regression to Predict MPG
#### Import the MechaCar_mpg.csv file and read into a dataframe
#
![dataframe](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/importdataframe.PNG)

#
![MechaCar](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/summarymecha.PNG)
#
### Summary
#
* Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
* Is the slope of the linear model considered to be zero? Why or why not?
* Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

#
## Summary Statistics on Suspension Coils
#
#### Import the Suspension_Coil.csv file and read into a dataframe
#
![Suspension](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/suspension.PNG)
#
#### Total Summary
#
![total summary](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/totalsummary.PNG)
#
#### Lot Summary
#
![lot summary](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/lotsummary.PNG)
#
* The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?
#

## T-Tests on Suspension Coils
### interpretation and findings for the t-test results
#### t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 PSI
#### all lots
t.test(Suspension_Coil$PSI,mu=mean(Suspension_Coil$PSI))
#
![t-testall](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestall.PNG)
#
#### lot 1
#
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot1"),mu=mean(Suspension_Coil$PSI))
#
![t-test1](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot1.PNG)
#### lot 2
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot2"),mu=mean(Suspension_Coil$PSI))
#
![t-test2](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot2.PNG)
#
#### lot 3
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot3"),mu=mean(Suspension_Coil$PSI))
#
![t-test3](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot3.PNG)



## Study Design: Statistical Study Comparing MechaCar vs. Competition

* What metric or metrics are you going to test?
* What is the null hypothesis or alternative hypothesis?
* What statistical test would you use to test the hypothesis? And why?
* What data is needed to run the statistical test?