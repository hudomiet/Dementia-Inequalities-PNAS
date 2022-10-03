# Dementia-Inequalities-PNAS
*** INTRODUCTION ***

This data repository includes all Stata and MATLAB program files used in the project "Trends in Inequalities in the Prevalence of Dementia in the U.S." by Peter Hudomiet, Michael D. Hurd, and Susann Rohwedder. The paper is currently (10/3/2022) conditionally accepted in the Proceedings of the National Academy of Sciences of the United States of America (PNAS). 

The objective of the project and the details of the statistical methods are discussed in the published article and its supplementary appendix.

With questions, please contact the corresponding author: Peter hudomiet (Peter_Hudomiet@rand.org)

The data repository incldues four zip files, each containing a set of progrgam codes:
1) DataCleaning.zip: Five Stata do files that clean and preprocess all the data used in the project. (Details below)
2) MCMC-Model.zip: Six MATLAB program files that estimate the cognitive status of each person in each survey wave.
3) PostEstimation.zip: Seven Stata do files that create all the tables and figures presented in the main paper.
4) SupplementaryFiles.zip: Eight Stata do files that create all the tables and figures in the supplemmntary appendix.


>>> DATA NEEDED <<<
The project used data from the core Health and Retirement Study (HRS) and its supplements available at https://hrs.isr.umich.edu/data-products. Most of the datafiles are publicly available upon registration on the HRS website. The ADAMS supplelemt is sensitive data. To access ADAMS, please follow the application procedure explaiend on the HRS webstie. 

To run the progrgams one needs to get access ot the following data files:
1) The HRS Tracker file, which includes basic identifiers and status variables. We used the the 2016 tracker file (TRK2106TR_R.dta), but this can be replaced with a newer tracker file.
2) The RAND-HRS Longitudinal File, which includes cleaned versions of the most important HRS variables. We used version 1 of the 2016 file (randhrs1992_2016v1.dta), but this could be replaced with newer data versions.
3) The RAND-HRS Detailed Imputation file, which includes additional imputed variables that are not part of the main RAND-HRS file. We used version 1 of the 2016 file (randhrsimp1992_2016v1.dta), but this could be replaced with newer data versions.
4) The 2000-2016 RAND-HRS fatfiles that inlcude all the uncleaned raw HRS data.
5) The Health and Retirement Study Imputation of Cognitive Functioning Measures, which incldues imputed cognition measures. These measures are normally added to the RAND-HRS dtaafile, but the randhrs1992_2016v1.dta did not yet include the 2016 wave of these measures. If newer RAND-HRS releases are used, this datafile may not be needed.
6)  The Aging, Demographics, and Memory Study (ADAMS), which is a supplemental study in the HRS that conducted in-person clinical assessments of cognitive status and dementia.


>>> THE PROGRAM FILES <<<
DataCleaning.zip includes five Stata do files:
1) Step0_Master.do: A master do file that calls the other files.
2) Step1_BasicVars.do: Merges the relevant datafiles together and applies basic data cleaning.
3) Step2_Cognition.do: Cleans the detailed cognition measures that are not part of he RAND-HRS Longitudinal file.
4) Step3_Adams.do: Cleans the ADAMS data.
5) Step4_FinalClean.do: Final cleaning of all datafile, including consistency checks, logical imputations, other initial imputations (missing data are imputed using multiple imputation in the MCMC model), labeling the variables, and saving the datafiles in Stata and txt. 

MCMC-Model.zip includes six MATLAB progrgam files:
1) Master_HRSdata_Release1.m: A master file that calls the other files, and saves the data.
2) DataLoad_Release1.m: Loads the txt datafiles and stores them in a MATLAB format.
3) MCMC_Estimate_Release1.m: Esitmates the MCMC model. This is the main esitmation file.
4) GaussHermite.m: An auxiliary file created by Geert Van Damme to determines the abscisas and weights for the Gauss-Hermite quadrature that I use for numerical integration. 
5) Master_SyntheticData_Release1.m: A master file used to estimate the same model on synthetic data with known parameter values.
6) DataCreate_Release1.m: Creates a synthetic data file with known parameter values.

PostEstimation.zip includes seven Stata do files:
1) 

SupplementaryFiles.zip

