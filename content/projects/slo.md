+++
title = "SLO Probation"
description = "better call slo"
weight = 1

[extra]
label = "w26-s26"
type = "🤓"
+++

(tldr; wanted interesting methods/results and discovered that the interesting part was everything else)

**What it is** 

A local validation study of risk-assessment tools used by the San Luis Obispo County Probation Department.

**Context** 

Unlike the other projects, this one was unique in that we were essentially hired out as contractors as part of the Data Science Capstone to people who didn't speak statistics.

Some jargon:

- "Local" = using location-specific data (in this case, SLO)
- "Validation" = testing the accuracy of the county's tools to predict recidivism
- "Recidivism" = getting in trouble again
- "Risk-assessment" = how likely someone get in trouble; important for when a court determines what the probation plan is (pretrial release, supervision, etc.)

Our job was to take their datasets of probation outcomes and evaluate the predictive performance for the different tools across outcomes and demographic groups. 

**What I did** 

1) Combined risk-assessment records with probation supervision data using unique IDs.
2) Cleaned dates, handled missingness, determined appropriate supervision windows, and constructed outcomes such as rearrest/reconviction from subsequent records.
3) Built separate validation pipelines for the tools (vs treating the assessments as interchangeable) based off literature from Sonoma County (also in California and very nice)
4) Used logistic regression and ROC/AUC (measures of predicted accuracy) to measure how well assessment scores predicted their intended outcomes.
5) Investigated performance across outcomes, time windows, and demographic groups.

**What was hard** 

- The department had a very strict data privacy policy (naturally, each row was someone's darkest moment), which included signing several NDAs, waiting several weeks per data request, and having to analyse the data through a school-secured Jupyter server
- Defining outcomes: we had to subjectively determine what counted as "recidivism" over what periods. We also had to choose which predictive variables were included; "domestic violence" should, but "unhoused"? "Marital status"? 
- Imbalanced subgroups: SLO is mostly White and Hispanic; you can imagine what would happen to a tool's predictions if it encountered an Asian woman when there weren't any in the data
- Along the lines of the above, several of the assessment datasets didn't overlap, and many outcomes were rare (ex: violent rearrests), which also skewed the evaluation
- What exactly counts as "fair"?

**What I learned**

- I was initially disappointed with how basic the tools were. Eventually, I realized that being saucy with the methods naturally introduces liability, which is absolutely not needed in a courtroom. In any case, I was plenty occupied by learning about criminal justice proceedings, how data science and the law intersect, etc. 
- Once again, making "local validation of risk-assessment tools 🤓" palatable to an audience during poster presentations was a challenge in comparison to more fun-sounding things like ancestries and seagulls. Was slightly harder to market than HexSim, but we made it work. 

**In hindsight**

In comparison to the ivory tower data science I was mostly working with thus far, it was refreshing to work with boots-on-the-ground statistics with real stakeholders on the other end. The idea of being "the translator" was a recurring theme that was reinforced by the end.

The tools worked fine; some range in predictive accuracy, but generally higher assessment scores corresponded with worse outcomes, so as far as anyone in the SLO Probation Dept is concerned, justice is served. 