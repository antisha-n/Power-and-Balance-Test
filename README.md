# Power-and-Balance-Test

This repository contains some sample code on conducting power calculations in STATA. All files are self contained and can be run independently from the other scripts. Please read the code preamble for more details on each file. 

I use in-built power commands in STATA to calculate sample size and minimum detectable effect size with or without covariates and with or without imperfect compliance in individual and clustered models. Both files can be run with any baseline dataset with a continuous outcome and binary treatment variable. 
The sample code uses the Balsakhi dataset (baroda_0102_1obs.dta) for illustration purposes. The file can also be run with other similar datasets with a continuous outcome and treatment variable.You can learn more about the Balsakhi dataset from the documentation and data here at https://doi.org/10.7910/DVN/UV7ERB.

I calculate power using a dummy dataset provided by J-PAL, simulated using an underlying sample distribution and a few design parameters. The underlying distribution and the design factors can be changed to suit the context of use.

