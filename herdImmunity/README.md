# Herd Immunity
COVID-19 Herd Immunity Thresholds in States and Metropolitan Statistical Areas (MSAs) across the United States

Contributors to this effort include the following researchers:
1. Abhishek Mallela, Department of Mathematics, University of California Davis
2. Jacob Neumann, Department of Biological Sciences, Northern Arizona University
3. Ye Chen, Department of Mathematics and Statistics, Northern Arizona University
4. Yen Ting Lin, Information Sciences Group, Computer, Computational and Statistical Sciences Division (CCS-3), Los Alamos National Laboratory
5. Richard G. Posner, Department of Biological Sciences, Northern Arizona University
6. William S. Hlavacek*, Theoretical Biology and Biophysics Group, Theoretical Division (T-6), Los Alamos National Laboratory<br>

*Corresponding author: William S. Hlavacek (wish@lanl.gov)

### Overview
When will the ongoing COVID-19 vaccination campaign allow the United States (US) to safely end nonpharmaceutical interventions? The answer depends partly on the herd immunity threshold (HIT), which is a function of the basic reproduction number, which characterizes disease transmission dynamics within a naïve population in the absence of any intervention. Because these dynamics are population-specific, the vaccination penetrance required to reach herd immunity may vary from community to community. Here, using Bayesian inference, we parameterized a compartmental model with regional surveillance data available for each of the 50 states and 384 metropolitan statistical areas (MSAs) in the US. This procedure allowed us to obtain state- and MSA-specific R<sub>0</sub> and HIT estimates. Using this information and estimates of disease burden based on serological data, we can determine the number of vaccinations required to reach herd immunity in each state and US MSA.

### Plots
Under ```/plots```, we provide diagnostic plots of our Markov Chain Monte Carlo (MCMC) sampling procedure for all 50 states. The methodology behind the procedure is described in our manuscript (in preparation).

### Supplementary files
In ```/supplement_files```, we provide the files corresponding to the Supplementary Information of our manuscript (in preparation).

### PyBioNetFit
PyBioNetFit is a general-purpose program for parameterizing biological models that are specified with the BioNetGen rule-based modeling language (BNGL) or the Systems Biology Markup Language (SBML).
The latest version of PyBioNetFit is available at https://github.com/lanl/PyBNF.
In ```/PyBNF```, data files (with an .exp extension) are provided for all 50 states and 384 MSAs, using data from January 21, 2020 to June 21, 2020 (inclusive dates).
These files aid in the reproducibility of our findings - as such, we have also provided sample files for the New York City Metro Area (under ```/PyBNF/sample_files```).

### Vaccine Countdown
Under ```/vaccine_countdown```, we summarize our findings with tables that provide the additional number of vaccinations needed for each state and each MSA to reach herd immunity. Our tables are conditioned on the dominance of the B.1.617.2 (Delta) variant, which allows us to account for increased transmissibility of the virus.

The column descriptors for each table are provided below:<br>
Column 1: Name of the state or MSA; reference for MSAs: https://en.wikipedia.org/w/index.php?title=List_of_metropolitan_statistical_areas&oldid=1002583892<br>
Column 2: Population size of the state or MSA<br>
Column 3: The herd immunity threshold (HIT) for a given region, given by HIT = 1 - 1/R<sub>0</sub><br>
Column 4: Our estimate for the population fraction with natural immunity, which is informed by seroprevalence data<br>
Column 5: The fraction of the population that has been vaccinated, which is given by vaccination data from the CovidActNow API: https://apidocs.covidactnow.org<br>
Column 6: The vaccine countdown number for a given region<br>
Column 7: Progress to herd immunity (as a percentage of the herd immunity threshold number of persons)<br>
