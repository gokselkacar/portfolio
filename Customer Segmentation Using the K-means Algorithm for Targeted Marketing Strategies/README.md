# Customer Segmentation and Targeted Marketing Strategy

## Objective
Develop a customer segmentation model to categorize customers into distinct groups based on their purchasing behavior and personal characteristics. Use this model to recommend targeted marketing strategies for a retail company.

## Dataset
“ Mall Customers ” dataset. This dataset typically includes customer information like age, gender, annual income, and spending
score.
 
## Steps
#### Data Exploration:
- Import the dataset and perform basic exploratory data analysis (EDA).

- Check for missing values, outliers, and understand the distribution of key
variables like age, income, and spending score.

#### Data Preprocessing:
- Clean the dataset by handling missing values and outliers.

- Normalize the data.

#### Customer Segmentation:
- Use the K-means algorithm to segment customers into groups.

- Determine the optimal number of clusters using methods like the elbow
method.

- Analyze the characteristics of each cluster.

#### Data Visualization:
- Visualize the clusters using scatter plots, highlighting different segments
with distinct colors.

- Use bar charts or pie charts to show the distribution of categorical
variables like gender within each cluster.

#### Insights and Strategy Formulation:
- Derive insights from the clustering results.

- Recommend targeted marketing strategies for each customer segment.


## Results

This is an independent, exploratory analysis of the 200-row Mall Customers dataset. The numeric summaries below come from the notebook's saved Cluster Summary tables. Cluster names in this README are one-based: notebook cluster 0 is Cluster 1, and so on, matching the plot labels.

The models use age and spending score, annual income and spending score, or age and annual income. Gender percentages are descriptive summaries, not inputs to these three models. Annual income uses the dataset's k$ units; spending score uses its 1-100 scale.

Marketing suggestions are hypotheses for customer research and controlled tests, not measured campaign outcomes. Age and gender do not establish family status, channel preference, brand loyalty or purchasing motives. Annual income does not establish disposable income or social class. Spending score does not measure the proportion of income spent, actual revenue, repeat purchasing or churn.

The original Mall_Customers.csv is not included in this repository. These are reconciled saved results, not a new clustering run. The notebook and its older narrative comments remain unchanged; the numeric output tables are the basis for the corrected descriptions here.

### Insights and Strategy Formulation from the Segmentation Model No.1

![download](https://github.com/user-attachments/assets/36231173-a1bd-43de-a778-35fabe54bb50)

**Cluster 1: mean age 27.62 years, mean spending score 49.15; 38.30% male and 61.70% female, n = 47.**

The mean spending score is moderate relative to the other groups in this model. The summary does not identify students, regular visitors or preferred brands.

**Cluster 2: mean age 43.29 years, mean spending score 15.02; 50.00% male and 50.00% female, n = 48.**

This group has the lowest mean spending score in Model 1. The score does not explain why it is low or identify household needs.

**Cluster 3: mean age 30.18 years, mean spending score 82.35; 42.11% male and 57.89% female, n = 57.**

This group has the highest mean spending score in Model 1. A cross-sectional score does not establish repeat spending, loyalty or a low churn rate.

**Cluster 4: mean age 55.71 years, mean spending score 48.23; 45.83% male and 54.17% female, n = 48.**

This group has a moderate mean spending score. Its age summary does not establish premium-product preferences or preferred shopping activities.

Correction: the earlier Cluster 4 description listed approximately 46% male and 56% female, totaling 102%. Saved notebook cluster 3 reports 45.83% male and 54.17% female; those source values are used above.

### Targeted Marketing Strategies for each Customer Segment in Segmentation Model No.1

The following proposals are testable hypotheses. No campaign result or causal effect was measured in this analysis.

**Moderate spending score, Cluster 1:**

- Hypothesis to test: Test a value offer against experience-led content, using channels supported by customer research. Measure campaign response rather than assigning a channel or product preference from age or gender.

**Low spending score, Cluster 2:**

- Hypothesis to test: Investigate shopping goals through customer research, then test a relevant offer against a control. Family-oriented promotions would need evidence of household needs.

**High spending score, Cluster 3:**

- Hypothesis to test: Test loyalty rewards or tailored recommendations against a control, using expressed interests or purchase records if available. Measure repeat purchases before making retention claims.

**Moderate spending score, Cluster 4:**

- Hypothesis to test: Test messages about value, quality or activities after checking customer interests. Compare measured responses without assuming premium tastes from age.

### Insights and Strategy Formulation from the Segmentation Model No.2

![download](https://github.com/user-attachments/assets/08250a36-fc2a-4a27-bcdc-4accfea44645)

**Cluster 1: mean annual income 25.73 k$, mean spending score 79.36; 40.91% male and 59.09% female, n = 22.**

This group combines relatively low annual income with a high spending score. It does not show that customers spend a large share of their income at the mall.

**Cluster 2: mean annual income 55.30 k$, mean spending score 49.52; 40.74% male and 59.26% female, n = 81.**

This is the largest group in Model 2 and has a moderate spending score. Keep it separate from the high-spending-score Cluster 1.

**Cluster 3: mean annual income 86.54 k$, mean spending score 82.13; 46.15% male and 53.85% female, n = 39.**

This group combines relatively high annual income with a high spending score. Luxury preferences and price sensitivity are not measured.

**Cluster 4: mean annual income 88.20 k$, mean spending score 17.11; 54.29% male and 45.71% female, n = 35.**

This group combines relatively high annual income with a low spending score. The data do not establish caution, savings priorities or a preference for expensive products.

**Cluster 5: mean annual income 26.30 k$, mean spending score 20.91; 39.13% male and 60.87% female, n = 23.**

This group combines relatively low annual income with a low spending score. Price sensitivity and product preferences require additional evidence.

Grouping correction: the saved mean spending scores are 79.36 for Cluster 1 and 49.52 for Cluster 2. The earlier strategy headings grouped both as high spending, and both as moderate spending. The hypotheses below distinguish them.

### Targeted Marketing Strategies for each Customer Segment in Segmentation Model No.2

The following proposals are testable hypotheses. No campaign result or causal effect was measured in this analysis.

**Lower annual income, high spending score, Cluster 1:**

- Hypothesis to test: Test a discount or bundle offer against a control. Measure incremental response and promotion costs; the spending score alone does not establish bargain-seeking behavior.

**Middle annual income, moderate spending score, Cluster 2:**

- Hypothesis to test: Test value-focused offers or recommendation formats separately for this group. Its mean spending score is 49.52, so it should not be grouped with Cluster 1 under a high-spending-score label.

**Higher annual income, high spending score, Cluster 3:**

- Hypothesis to test: Test premium-oriented messaging against value-oriented messaging after checking expressed interests. Treat a luxury preference as a hypothesis rather than an income-based conclusion.

**Higher annual income, low spending score, Cluster 4:**

- Hypothesis to test: Research reasons for limited engagement, then compare relevant offers or product information against a control. Do not infer cautious spending or preferred product quality from these two variables.

**Lower annual income, low spending score, Cluster 5:**

- Hypothesis to test: Test clear pricing, bundles or loyalty offers where customer research supports them. Evaluate response and cost without inferring financing needs or gender-specific product preferences.

### Insights and Strategy Formulation from the Segmentation Model No.3

![download](https://github.com/user-attachments/assets/034a56a6-7ae7-4a62-a9c1-857de3927501)

**Cluster 1: mean age 31.96 years, mean annual income 72.96 k$; 46.58% male and 53.42% female, n = 73.**

These are age and annual-income summaries. They do not establish technology use, lifestyle or preferred communication channels.

**Cluster 2: mean age 55.81 years, mean annual income 51.78 k$; 50.00% male and 50.00% female, n = 54.**

These are age and annual-income summaries. They do not establish health needs, purchasing impulsiveness or brand loyalty.

**Cluster 3: mean age 39.00 years, mean annual income 106.50 k$; 41.67% male and 58.33% female, n = 24.**

These are age and annual-income summaries. They do not identify parents, household composition or luxury preferences.

**Cluster 4: mean age 30.35 years, mean annual income 29.27 k$; 34.69% male and 65.31% female, n = 49.**

These are age and annual-income summaries. They do not identify students, career stage, disposable income or fashion preferences.

### Targeted Marketing Strategies for each Customer Segment in Segmentation Model No.3

The following proposals are testable hypotheses. No campaign result or causal effect was measured in this analysis.

**Age and income group, Cluster 1:**

- Hypothesis to test: Ask about channel and product preferences, then test relevant content or events. Digital-channel preference is a hypothesis to validate, not a finding from mean age.

**Age and income group, Cluster 2:**

- Hypothesis to test: Test value or quality messages where customer research supports them. Health-oriented campaigns or particular channels require evidence beyond age and income.

**Age and income group, Cluster 3:**

- Hypothesis to test: Test recommendations or service formats based on declared interests. Family-related offers require household information that this dataset does not contain.

**Age and income group, Cluster 4:**

- Hypothesis to test: Test transparent value offers and compare suitable channels after gathering preference data. Student discounts require verified eligibility rather than an inference from age or income.

### Evidence and limitations

Numeric source: the saved [segmentation notebook](./Customer%20segmentation%20using%20the%20K-means%20algorithm%20for%20targeted%20marketing%20strategies..ipynb), in the three cells headed Analysis of the characteristics of each cluster. Values are reported to the two decimal places shown there. For example, Model 3 Cluster 2 has mean age 55.81 in the saved output, replacing the earlier prose value of 58.

Cluster assignments and summaries depend on feature choices, scaling, initialization and the observed sample. The groups describe this dataset; they do not by themselves establish customer motives or generalize to a live retail population. Validate proposed campaigns with customer research, consented behavioral data and appropriately designed experiments before applying them.
