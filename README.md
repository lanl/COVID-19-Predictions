# COVID-19-Predictions
Daily Forecasting of New Cases for Regional Epidemics of Coronavirus Disease 2019 with Bayesian Uncertainty Quantification

This is a research product of the U.S. Department of Energy (DOE) Office of Science’s National Virtual Biotechnology Laboratory (NVBL), a consortium of national laboratories (Argonne, Los Alamos, Oak Ridge, and Sandia) focused on responding to COVID-19. The objectives of this effort are 1) near real-time situational awareness, 2) predictive analytics, and 3) a web platform providing policy-makers and the public access to NVBL predictions.

This repository archives predictions from models for regional COVID-19 epidemics. Bayesian inference is used to quantify uncertainty in daily forecasts of expected reporting of new cases, enabling identification of new trends in surveillance data.

The methodology is described in ```/methodology/Manuscript-draft.pdf```. This repository only archives the compartmental model described in the manuscript. A preprint is available: https://arxiv.org/abs/2007.12523

Contributors to this effort include the following researchers:
1. Yen Ting Lin*, Information Sciences Group, Computer, Computational and Statistical Sciences Division (CCS-3), Los Alamos National Laboratory
2. Jacob Neumann, Department of Biological Sciences, Northern Arizona University
3. Ely F. Miller, Department of Biological Sciences, Northern Arizona University
4. Richard G. Posner, Department of Biological Sciences, Northern Arizona University
5. Abhishek Mallela, Department of Mathematics, University of California Davis
6. Cosmin Stafa, Sandia National Laboratory
7. Jaideep Ray, Sandia National Laboratory
8. Gautum Thakur, Oak Ridge National Laboratory
9. Supriya Chinthavali, Oak Ridge National Laboratory
10. William S. Hlavacek, Theoretical Biology and Biophysics Group, Theoretical Division (T-6), Los Alamos National Laboratory<br>

*Corresponding author: Yen Ting Lin (yentingl@lanl.gov)

### Statistical inference and proababilistic prediction for regional epidemics.
Our Bayesian model uses regional daily reported case counts to infer the progression of regional epidemics. The model output is probabilistic, meaning that, instead of predicting an absolute value (e.g., we predict that there will be 279 new cases tomorrow), the model provides the probabilities of the new case counts (e.g., we predict with a probability 90% that the new case count is below 425). 

Under ```dailyForecasts```, we provide daily forecasts for two types of regions: we provide statistical inference and probabilistic predictions for the 15 most populous Meropolitan Statistical Areas (MSAs) and the 50 US States daily. The output of the analysis for each region is reported in a date-labeled folder (e.g., ```2020-07-26```) as a .csv file. In the date folder, we provide a summary figure, wherein the results are visualized as in the figure below (which is for the New York City MSA, and the analysis was performed on 2020-06-21):
<p align="center">
<img src='https://github.com/lanl/COVID-19-Predictions/blob/master/figs/UQBand-mechanistic.png' width='80%'>
</p>
The color bands in these figures represent our *belief* of the progression of the regional epidemics, inferred from the data, visualized as discrete markers. The outermost (widest) band visualizes that, with 95% probability, we believe that the reported cast counts - in the past and in the future - should be within this band. The median prediction, which is visualize as a thin purple line, represents a central measure of prediction probability density.

Our Bayesian model is designed to address the fact that regional daily case reports are often very noisy. **The fundamental question is, when we see a new data point that is higher than the "average" (broadly defined, such as a moving-window average), is the new data point attributable to statsitical noise or is the epidemic really upward-trending?** This type of *Bayesian uncertainty quantification* (UQ) provides useful insights into whether a new data point is consistent with our current belief of the disease progression subject to the statistical noise. If the new data point is not consistent, it is likely that it is caused by a fundamental change of the dynamics, for example, relaxed social-distancing measures. The results from our analysis can thus be used to **increase situational awareness** and to **provide early warning signals** of when new case counts are upward trending. 

### Compartmental Model used for mathematical model-based inference

We use mathematical model-based inference. Specifically, in our analysis, we found that compartmental models are expressive and flexible, more so than curve-fitting models, and are able to capture a variety of regional dynamics seen in the data. Our compartmental model describes the population dynamics and the interactions between the *S*usceptible, *E*xposed (infected but yet to show symptoms), *I*nfected, *H*ospitalized, *R*ecovered, and *D*eceased populations. Importantly, we also model the behavior of social distancing and quarantine/self-isolation. Although there are many model parameters (>18), we estimated and fixed most of them on the basis of exisiting epidemiological studies of COVID-19 and infer only 6 region-specific free parameters. We verified in the manuscript that the model is *identifiable*.
<p align="center">
<img src='https://github.com/lanl/COVID-19-Predictions/blob/master/figs/compartmentalModel.png' width='60%'>
</p>

### An *online-learning* effort to monitor distinct episodes of social-distancing 

In our modeling framework, we allow for distinct episodes of social-distancing behavior (at the population level). The onset and termination of an episode are inferred continuously as new data comes in. With this online-learning effort, we can continuously parameterize the model to capture the dynamics of natural social distancing and social-distancing promoted by government mandates (e.g., stay-at-home/shelter-in-place orders). <br>

Below is our analysis showing a one-phase model which assumed the social-distancing behavior of the Phoenix MSA is temporally constant: <br>
<p align="center">
<img src='https://github.com/lanl/COVID-19-Predictions/blob/master/figs/Figure 10A.png' width='40%'>
</p>
and a two-phase model which assumed a change of behavior at an unknown time:<br>
<p align="center">
<img src='https://github.com/lanl/COVID-19-Predictions/blob/master/figs/Figure 10B.png' width='40%'>
</p>
We are able to infer from the data that with 95% probability, a behavioral change of the population occurred betwen 2020-05-20 and 2020-05-27. Our inferred result is consistent with the fact that the stay-at-home order of the State of Arizona expired on 2020-05-15.

We also perform model selection between the multi-phase models. The best model is used to predict the progression two weeks into the future.
