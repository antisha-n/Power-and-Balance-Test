# Power-and-Balance-Test

The sensitivity of an experiment to detect differences between the treatment and the control groups is measured by statistical power.  

A type I error is a false positive: falsely rejecting the null hypothesis of no effect, or falsely concluding that the intervention had an effect when it did not. The probability of committing type I error is known as α.

A type II error is a false negative: failing to detect an effect when there is one. The probability of committing type II error is typically given by β. To differentiate it from the treatment effect β, in this resource we denote type II errors by κ.

Power is the probability of rejecting a false null hypothesis. Formally, power is typically given by 1-β. Again, to differentiate power from the treatment effect β, in this resource we will denote power by 1-κ. That is, maximizing statistical power is to minimize the likelihood of committing a type II error. 

Power calculations involve either determining the sample size needed to detect the minimum detectable effect (MDE) given other parameters, or determining the effect size that can be detected given a set sample size and other parameters. Power is also affected by the design of the evaluation, the take up of the treatment, and the attrition rate, discussed in greater detail below. 

This repository contains some sample code on conducting power calculations in STATA. All files are self contained and can be run independently from the other scripts. Please read the code preamble for more details on each file. 

I use in-built power commands in STATA to calculate sample size and minimum detectable effect size with or without covariates and with or without imperfect compliance in individual and clustered models. Both files can be run with any baseline dataset with a continuous outcome and binary treatment variable. 
The sample code uses the Balsakhi dataset (baroda_0102_1obs.dta) for illustration purposes. The file can also be run with other similar datasets with a continuous outcome and treatment variable.You can learn more about the Balsakhi dataset from the documentation and data here at https://doi.org/10.7910/DVN/UV7ERB.

About the data: The Balsakhi program was a remedial education program that was conducted in Indian schools to increase literacy and numeracy skills. 
You can learn more about the Balsakhi dataset from the documentation and data here at https://doi.org/10.7910/DVN/UV7ERB

Variables:
- Outcome of interest is in the "normalised total score." This is represented by: 
	- "pre_totnorm" at baseline
	- "post_totnorm" at the endline
- Treatment: bal
	- 0=control
	- 1=treatment
- Clustering variable (by school): divid

Note: key inputs for calculating power like the mean and the standard deviation at baseline, ICC, etc. are calculated 
using the specified dataset, but they can also be specified manually.

About the file:
- This file contains sample code for the following:
	0. Housekeeping and load data
	1. No covariates
		1a. Sample size for a given effect size
		1b. MDE for a given sample size
	2. With covariates (not applicable for binary data)
		2a. Sample size for a specified effect - with covariates 
		2b. MDE for a given sample size - with covariates
	3. Sample size with Partial Take-up
	4. Overview of how MDE and sample size change as we add covariates and take-up changes
	5. Clustered designs
		5a. Compute number of clusters for a given effect size and size of cluster 
		5b. Compute cluster size given the number of clusters and effect size 
		5c. Compute effect size for a given cluster size and number of clusters

I calculate power using a dummy dataset provided by J-PAL, simulated using an underlying sample distribution and a few design parameters. The underlying distribution and the design factors can be changed to suit the context of use.

