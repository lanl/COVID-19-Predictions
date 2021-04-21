# COVID-19-Predictions
COVID-19 Herd Immunity Thresholds in Metropolitan Statistical Areas (MSAs) across the United States

Contributors to this effort include the following researchers:
1. Abhishek Mallela, Department of Mathematics, University of California Davis
2. Jacob Neumann, Department of Biological Sciences, Northern Arizona University
3. Yen Ting Lin, Information Sciences Group, Computer, Computational and Statistical Sciences Division (CCS-3), Los Alamos National Laboratory
4. William S. Hlavacek*, Theoretical Biology and Biophysics Group, Theoretical Division (T-6), Los Alamos National Laboratory<br>

*Corresponding author: William S. Hlavacek (wish@lanl.gov)

### Overview

As the COVID-19 pandemic continues to unravel across the United States, the task of reaching herd immunity is a non-trivial one. Using a mechanistic compartmental model (Y.T. Lin et al., Daily Forecasting of Regional Epidemics of Coronavirus Disease with Bayesian Uncertainty Quantification, United States. Emerg Infect Dis 27, 767-778 (2021)), we improve the auxiliary measurement model and conduct further mathematical and numerical analyses. We extend the work done by Lin et al. by accounting comprehensively for all 384 MSAs in the 50 states of the US. Each MSA is parameterized using the inference procedure with Bayesian uncertainty quantification as described in Lin et al. We derive an expression for the COVID-19 basic reproduction number, R0, in the absence of any social distancing or protective mask-wearing measures. We then use R0 to obtain the herd immunity threshold in each MSA, for the dates from January 21, 2020 to September 21, 2020 (inclusive). Furthermore, we obtain vaccination data across the US at the county level annotated in the CovidActNow database, and we use that information to provide estimates of the number of additional vaccinations necessary to reach the herd immunity threshold in each MSA.

Under ```countdown```, we summarize our findings with a table that provides the additional number of vaccinations needed for each MSA to reach herd immunity. The herd immunity threshold (HIT) can be obtained for each MSA by a simple relationship with R0; in particular, HIT = 1-1/R0. By using Bayesian uncertainty quantification and extracting data on completed vaccinations from CovidActNow, we were able to calculate the number of additional vaccines that would have to be administered within each MSA in order for the corresponding subpopulation to reach herd immunity.

The column descriptors for the table are provided below:
Column 1: Ranking of MSA (from greatest to least in population size)
Column 2: Name of the Metropolitan Statistical Area (MSA)
Column 3: Median estimate of R0
Column 4: Estimate for the lower endpoint of the equal-tailed credible interval of R0
Column 5: Estimate for the upper endpoint of the equal-tailed credible interval of R0
Column 6: Median estimate of HIT
Column 7: Estimate for the lower endpoint of the equal-tailed credible interval of HIT
Column 8: Estimate for the upper endpoint of the equal-tailed credible interval of HIT
Column 9: Median estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the detected number of new cases
Column 10: Lower endpoint estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the detected number of new cases
Column 11: Upper endpoint estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the detected number of new cases
Column 12: Median estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the inferred number of new cases
Column 13: Lower endpoint estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the inferred number of new cases
Column 14: Upper endpoint estimate of the proportion of additional vaccinations necessary to reach herd immunity, using the inferred number of new cases
Column 15: the additional number of vaccinations needed to reach herd immunity
