# Ordinal regression in brms

This repository contains data and an R markdown document walking through an example of ordinal regression in `brms`. 

The data is from a study by Michael Correll and colleagues' CHI 2020 paper, _Truncating the Y-Axis: Threat or Menace?_
Specifically, their second experiment compares a couple of design variations of bar charts which signal that the y-axis has been truncated (i.e., does not start at zero). They measure chart users' subjective impressions of effect size (i.e., the difference between bars) using a 5-point Likert-style scale. Using ANOVA to analyzed these responses they do not find enough evidence to reject the null hypothessis that there is no difference in perceived effect size between these alternative visualization designs.

Bayesian ordinal regression has a couple advantages over ANOVA when modeling this sort of data:
1. Ordinal regression predicts responses on the discretized response scale, rather than assuming responses can take on continuous values. That being said, we can still average together these discrete posterior predictions to get estimates on a continuous scale.
2. `brms` allows us to model the dispersion of responses as well as their central tendency. This means that we can better account for variability in how the response scale is used.
3. Because this is a Bayesian model, when we estimate the difference between visualization designs, we can actually talk about evidence in favor of the null hypothesis, rather than "failure to reject the null". In the case of this experiment, this enables us to make stronger claims, e.g., that Correll et al. find no reliable effect on distortions in perceived effect size when they design bar charts in was that signal axis truncation.

You can read about Bayesian oridinal regression in Paul Bürkner's wonderful `brms` package in [this paper](https://osf.io/gyfj7/download).