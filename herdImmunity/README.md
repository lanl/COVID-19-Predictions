# COVID-19-Predictions
COVID-19 Herd Immunity Thresholds in Metropolitan Statistical Areas (MSAs) across the United States

Contributors to this effort include the following researchers:
1. Abhishek Mallela, Department of Mathematics, University of California Davis
2. Jacob Neumann, Department of Biological Sciences, Northern Arizona University
3. Yen Ting Lin, Information Sciences Group, Computer, Computational and Statistical Sciences Division (CCS-3), Los Alamos National Laboratory
4. William S. Hlavacek*, Theoretical Biology and Biophysics Group, Theoretical Division (T-6), Los Alamos National Laboratory<br>

*Corresponding author: William S. Hlavacek (wish@lanl.gov)

### Overview

When will the ongoing COVID-19 vaccination campaign allow the United States (US) to fully reopen? The answer depends on the classical herd immunity threshold (HIT), which is a function of the basic reproduction number , which characterizes disease transmission dynamics within a naïve population in the absence of any intervention. Because these dynamics are population-specific, the vaccination penetrance required to reach herd immunity may vary from community to community. Here, using Bayesian inference, we parameterized a compartmental model with regional surveillance data available for each of the 384 metropolitan statistical areas (MSAs) in the US. This procedure allowed us to obtain MSA-specific  and HIT estimates, as well as information about how the number of COVID-19 cases reported for each region relates to the actual disease burden. Using these results, we can determine the number of vaccinations required to reach herd immunity in each US MSA.

Under ```countdown```, we summarize our findings with a table that provides the additional number of vaccinations needed for each MSA to reach herd immunity. The herd immunity threshold (HIT) can be obtained for each MSA by a simple relationship with R0; in particular, HIT = 1-1/R0. By using Bayesian uncertainty quantification and extracting data on completed vaccinations from CovidActNow, we were able to calculate the number of additional vaccines that would have to be administered within each MSA in order for the corresponding subpopulation to reach herd immunity.

The column descriptors for the table are provided below:

Column 1: Ranking of MSA (from greatest to least in population size). Reference: https://en.wikipedia.org/wiki/List_of_metropolitan_statistical_areas

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
