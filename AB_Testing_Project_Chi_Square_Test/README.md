### A/B Testing - Comparison of Button Performances on the Montana State University Library Website

Independent portfolio analysis of existing Montana State University Library navigation-test data. The project compares click-through rates for five button labels using chi-square tests and develops a follow-up UX recommendation.

Hypothesis tests assess the evidence against a specified null model under their assumptions. A non-significant result does not establish equal performance or prove that an observed difference is solely due to chance.

______________________________ 


### 1. BUSINESS PROBLEM / PROJECT OBJECTIVE

The existing dataset compares the original Interact label with four alternatives: Connect, Learn, Help and Services. Performance is measured using click-through rate, calculated as button clicks divided by page visits.

This case study reports an independent analysis and a proposed follow-up. It does not document a university commission, an implementation by me or a measured uplift from my work.

<img width="1000" alt="Screen Shot 2023-04-22 at 6 42 57 PM" src="https://user-images.githubusercontent.com/90986708/233796469-6bb38ade-83e8-4915-ae69-92efefd4a713.png">


______________________________

### 2. PROJECT STEPS

1. Business Problem
2. Data Understanding & Preparing
3. A/B Testing (Chi-square Test)

______________________________

### 3. PROJECT RESULTS

The saved [notebook](./AB_Testing_Project_Chi_Square_Test.ipynb) contains the following counts and observed click-through rates:

| Label | Button clicks | Page visits | Observed CTR |
| --- | ---: | ---: | ---: |
| Interact | 42 | 10,283 | 0.4084% |
| Help | 38 | 3,180 | 1.1950% |
| Services | 45 | 2,064 | 2.1802% |
| Connect | 53 | 2,742 | 1.9329% |
| Learn | 21 | 2,747 | 0.7645% |

The overall five-version chi-square test returned p = 4.8523e-20, providing evidence that the click-through rates differ across versions under the test assumptions. This overall result does not establish which individual pairs differ.

Services and Connect have the highest observed CTRs. Their uncorrected chi-square comparison returned p = 0.54815 at alpha = 0.05. It did not detect a statistically significant difference between those two labels. This does not establish equal CTRs or prove that the observed gap is solely due to chance.

The notebook narrows the candidates through repeated, data-dependent elimination. Treat that selection as exploratory; it does not demonstrate that Services and Connect each significantly outperform every other label in a planned, multiplicity-adjusted pairwise analysis.

__________________________________

#### Recommendations:

- Shortlist Services and Connect for a focused follow-up comparison. Services has the higher observed CTR in this dataset, but the existing comparison does not establish it as superior to Connect.
- Define the primary metric, a practically meaningful effect, sample size and stopping rule before collecting new data. Report effect sizes and confidence intervals, and account for multiple comparisons when testing several labels.
- Check task completion and user expectations alongside clicks. Claims about homepage-return rates or student preferences need separate supporting evidence; they are not established by the inspected CTR calculations.

These values reconcile the README with the notebook's saved counts and outputs. The original CSV files are not included in this repository, so this documentation correction does not reproduce the original data collection or establish the experimental assignment procedure. The notebook code and narrative remain unchanged.
