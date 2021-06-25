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

Under ```herdImmunity```, we summarize our findings with a table that provides the additional number of vaccinations needed for each MSA to reach herd immunity. The herd immunity threshold (HIT) can be obtained for each MSA by a simple relationship with R0; in particular, HIT = 1 - 1/R_0.

The column descriptors for the table are provided below:

Column 1: Name of the Metropolitan Statistical Area (MSA) - Reference: https://en.wikipedia.org/wiki/List_of_metropolitan_statistical_areas

Column 2: Detected number of cumulative new cases 

Column 3: Model-inferred number of cumulative new cases 

Column 4: Number of completed vaccinations

Column 5: Number of additional vaccinations needed to reach herd immunity

Column 6: Progress to herd immunity (as a percentage of the herd immunity threshold)
