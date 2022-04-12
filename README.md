# MechaCar_Statistical_Analysis
## Linear Regression to Predict MPG
#### Import the MechaCar_mpg.csv file and read into a dataframe
#
![dataframe](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/importdataframe.PNG)
#
Linear regression using the lm() function with all six variables, followed by the summary() function to determine the p-value and the r-squared value for the linear regression model.
#
![MechaCar](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/summarymecha.PNG)
#
### Summary
#
Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
#
A 95% level of confidence was predetermined, meaning the p-value should be compared to alpha = .05 level of significance to verify if statistically significant.  The absolute minimum is -19.4701, the absolute maximum is 18.5849, showing fairly close tails for a normal distribution.  The median is -0.0692, very close to 0.  
#
Coefficients:
* mpg: 0 < .05, statistically significant, non-random amount of variance
* vehicle length: 0 < .05, statistically significant, non-random amount of variance
* vehicle weight: .08 > .05 not statistically significant, random amount of variance
* spoiler angle: .31 > .05 not statistically significant, random amount of variance
* ground clearance: 0 < .05 statistically significant, non-random amount of variance
* AWD: .19>=.05 not statistically significant, random amount of variance
#
Significant: vehicle length, and ground clearance represent non-random amounts of variance with respect to the mpg values
#
Is the slope of the linear model considered to be zero? 
#
Slopes:
#
The slope is non-zero for all variables, although vehicle weight and spoiler angle are close to zero.
* vehicle length 6.267
* vehicle weight .001
* spoiler angle .069
* ground clearance 3.546
* AWD -3.411


#### Does this linear model predict mpg of MechaCar prototypes effectively? 
R-squared is 0.7149, adjusted R-squared is 0.6825.  This linear model has a strong correlation with the dataset
and should predict mpg of MechaCar prototypes effectively, provided there are not other variables outside of the
dataset contributing to the variaton of the mpg.  The R-squared variable indicates about 71% of all mpg predictions
will be effectively determined with this linear model.
#
### Summary Statistics on Suspension Coils
#
The Suspension_Coil.csv file is comprised of datasets of testing weight capacities of various suspension coils from 3 production lots to determine overall consistency.
#### Import the Suspension_Coil.csv file and read into a dataframe
#
![Suspension](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/suspension.PNG)
#
#### Total Summary
#
Summary statistics of all of the manufacturing lots are shown in the table below. The mean is 1498.78 and the median is 1500 for this sample.
![total summary](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/totalsummary.PNG)
#
#### Lot Summary
#
Statistics for each of the 3 lots are shown below.  The mean and median are close to 1500 for each lot.
#
![lot summary](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/lotsummary.PNG)
#
* The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? 
#
The variance for all of the lots is 62.29356, which is < 100.  However, the variance for lot 3 is 170.2861224, which is >100.
Lots 1 (variance 0.9795918) and 2 (variance 7.4693878) meet the design specifications as individual lots, while lot 3 on it's own does not, 
but as part of all 3 lots, it does.
#

### T-Tests on Suspension Coils: Interpretation and findings for the t-test results
#### t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 PSI
#### all lots
#
All lots
p-value = 1   Since the p-value >.05 the common significance level, there is not enough evidence to reject the null hypothesis for all of the lots as a dataset.
#
t.test(Suspension_Coil$PSI,mu=mean(Suspension_Coil$PSI))
#
![t-testall](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestall.PNG)
#
#### lot 1
#
Lot 1
p-value = 1   Since the p-value >.05 the common significance level, there is not enough evidence to reject the null hypothesis for lot 1.
#
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot1"),mu=mean(Suspension_Coil$PSI))
#
![t-test1](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot1.PNG)
#### lot 2
#
p-value = .6072   Since the p-value >.05 the common significance level, there is not enough evidence to reject the null hypothesis for lot 2.
#
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot2"),mu=mean(Suspension_Coil$PSI))
#
![t-test2](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot2.PNG)
#
#### lot 3
#
p-value = .04168   Since the p-value <.05 the common significance level, there is enough evidence to reject the null hypothesis for lot 3.
#
t.test(subset(Suspension_Coil$PSI,Suspension_Coil$Manufacturing_Lot == "Lot3"),mu=mean(Suspension_Coil$PSI))
#
![t-test3](https://github.com/jcsargis00/MechaCar_Statistical_Analysis-/blob/main/images/ttestlot3.PNG)
#
### Summary
For each individual lot, Lot 1 had a p-value of 1 and Lot 2 had a p-value of 0.6072, both statistically similar which means we cannot reject the null hypothesis. For Lot 3, the sample mean is 1496.14 with a p-Value of 0.04168, lower than the significance level of 0.05, which indicates that the sample mean and the presumed population mean are not statistically different.


## Study Design: Statistical Study Comparing MechaCar vs. Competition
In order to compare MechaCar pricing compared to vehicles from other manufacturers, additional metrics could be added to
test the null hypothesis and the alternative hypothesis.  
### Data to be collected
Data would be collected on MechaCar and its comparable models from the last 2 years.  Data about additional features would be be incorporated and tested as metrics.
### Metrics to be tested
Selling Price (independent variable), Engine Type: Gasoline, Electric, or Hybrid (independent variable), Average Maintenance Cost of Ownership (independent variable), Average Insurance Cost, MPG, Creature comforts ratings (iPod, cup holders, GPS)
### Hypotheses: Null and Alternative
Null Hypothesis: MechaCar is priced correctly based on its performance across multiple metrics compared to similar cars 
#
Alternative Hypothesis: MechCar is not priced correctly based on its performance across multiple metrics compared to similar cars
### Statistical Test to be used
Multiple linear regression tests would be used to find the variables with the highest correlation with the selling price, and which combination of variables has the best impact on price.

