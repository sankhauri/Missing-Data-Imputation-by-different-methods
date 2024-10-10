## Abstract
Missing values are usually attributed to human error when processing data, machine error due to the malfunctioning of equipment, respondents’ refusal to answer certain questions, drop-out in studies and merging unrelated data. The missing values problem causes different issues like performance degradation, data analysis problems and biased outcomes lead by the differences in missing and complete values [1]. Moreover, the seriousness of missing values depend in part on how much data is missing, the pattern of missing data, and the mechanism underlying the missingness of the data [2,3]. Missing values can be handled by certain techniques including, deletion of instances and replacement with potential or estimated values, a technique denoted as imputation. 

In this project, we consider a dataset called water_potability which determines the water quality depending on the 9 features. Our goal is to conduct a comparative study of different missing value imputation methods to identify the method which yields the best predictive model for our response that is whether the water is worth drinking or not.

## Methodology
The dataset exhibits a Missing Completely at Random (MCAR) mechanism, a conclusion supported by the significantly high p-value obtained from the LittleMCAR test. However, opting for the straightforward approach of deleting missing rows poses a substantial risk of information loss, particularly given the dataset's modest size and the relatively high percentage of missing values.

To address this challenge, we've chosen five distinct imputation methods for this project: Mean Imputation, Hot Deck Imputation, Mice with pmm and cart, and Amelia-II.  With the exception of mean imputation, these methods represent advancements over traditional missing data techniques, providing unbiased estimates in scenarios involving both MCAR and Missing at Random (MAR) data.
Our subsequent focus involves a comparative analysis of these four imputation methods. Briefly, the methodologies are outlined as follows.

### Mean Imputation: This is the most simplistic method for continuous variables where we replace the missing values with the mean of the observed values of that variable. 

### MICE: Multiple Imputation with Chained Equations (MICE) assumes that the missing data are Missing at Random (MAR), which means that the probability that a value is missing depends only on observed value and can be predicted using them. It imputes data on a variable-by-variable basis by specifying an imputation model per variable. It has options like “pmm”,” cart” etc. 

### Sequential Hot Deck Imputer:  is a method used for imputing missing values in a dataset. In this approach, missing values are replaced with observed values from similar cases within the same dataset. The term "hot deck" refers to a pool of potential donors, and "sequential" indicates the order in which the imputation occurs. Assumes missing data is MAR or MCAR.

### Amelia II: This package (Amelia II) is named after Amelia Earhart, the first female aviator to fly solo across the Atlantic Ocean. History says, she got mysteriously disappeared (missing) while flying over the Pacific Ocean in 1937, hence this package was named to solve missing value problems. This package also performs multiple imputation (generate imputed data sets) to deal with missing values. Multiple imputation helps to reduce bias and increase efficiency.  It is enabled with bootstrap based EMB algorithm which makes it faster and robust to impute many variables including cross sectional, time series data etc. The reader can check reference [7] for more information.



## Reference: 
[1] Ayilara OF, Zhang L, Sajobi TT, Sawatzky R, Bohm E, Lix LM. Impact of missing data on bias and precision when estimating change in patient-reported outcomes from a clinical registry. Health Qual Life Outcomes. 2019;17(1):106. 
[2] Little, R.J.A. (1992). Regression with missing X's: A review. Journal of the American Statistical Association, 87, 1227-1237. 
[3] Little, R.J.A., & Rubin, D.B. (1987). Statistical Analysis with Missing Data. New York: John Wiley & Sons.
[4] Therese D Pigott (2001). A review of methods for missing data, Educational Research and Evaluation 2001, Vol. 7, No. 4, pp. 353-383.
[5] Schafer, J. L., & Graham, J. W. (2002). Missing data: Our view of the state of the art. Psychological Methods, 7,147−177.
[6] Emmanuel, T., Maupong, T., Mpoeleng, D. et al. A survey on missing data in machine learning. J Big Data 8, 140 (2021).
[7] Amelia II – “A program for missing Data”, J. Honaker, G. King, M. Blackwell (Journal of Statistical Software, 2011)
Data source: https://www.kaggle.com/code/kaanboke/the-most-used-methods-to-deal-with-missing-values/input

