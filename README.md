# Practical Application III: Bank Term Deposit Subscription Prediction

## Project Overview
This repository contains a Jupyter notebook that explores a dataset from a Portuguese banking institution and builds classification models to predict whether a client will subscribe to a term deposit based on various features such as age, job, previous marketing outcomes, and economic indicators. The goal of this project is to provide the bank with insights that can optimize their marketing strategies and increase the success rate of term deposit subscriptions.

## Data

### Overview
The data for this project is from a Portuguese bank's marketing campaigns and includes client and economic information. The dataset is used to develop models that predict whether a client will subscribe to a term deposit based on these features.

### Key Variables
- **Age**: The age of the client.
- **Job**: The type of job the client has (e.g., admin, blue-collar, entrepreneur).
- **Marital Status**: The marital status of the client (e.g., married, single, divorced).
- **Education**: The level of education the client has attained.
- **Default**: Whether the client has credit in default.
- **Housing Loan**: Whether the client has a housing loan.
- **Personal Loan**: Whether the client has a personal loan.
- **Contact Communication Type**: How the client was contacted (e.g., cellular, telephone).
- **Last Contact Month**: The last month in which the client was contacted.
- **Pdays**: Number of days since the client was last contacted in a previous campaign. A value of 999 indicates that the client was not previously contacted.
- **Previous**: The number of contacts performed before this campaign.
- **Poutcome**: The outcome of the previous marketing campaign.
- **Economic Indicators**: Various economic factors such as employment variation rate, consumer price index, consumer confidence index, euribor 3-month rate, and the number of employees.

### Preprocessing
Data preprocessing involved handling missing values, encoding categorical variables using one-hot encoding, and creating new features such as a binary indicator for whether the client was contacted in a previous campaign. The `pdays` feature was handled carefully by replacing the value of 999 with `NaN` and creating an additional binary feature indicating if the client had been contacted before.

### Visualization of the Data
Below are plots showing the distribution of term deposit subscriptions by different client attributes, which helps in understanding which features might be most influential in predicting subscriptions.

![Subscription Distribution by Job](/plots/subscription_distribution_job.png)

![Subscription Distribution by Education Level](/plots/subscription_distribution_education.png)

![Subscription Distribution by Marital Status](/plots/subscription_distribution_marital.png)

![Subscription Distribution by Contact Type](/plots/subscription_distribution_contact.png)

![Subscription Distribution by Age](/plots/subscription_distribution_age.png)

![Subscription Distribution by Euribor 3 Month Rate](/plots/subscription_distribution_euribor3m.png)

![Subscription Distribution by Month](/plots/subscription_distribution_month.png)

![Subscription Distribution by Days Since Previous Campaign Contact](/plots/subscription_distribution_pdays.png)

These visualizations provides insights into which attributes are most strongly associated with term deposit subscriptions, guiding the feature selection process.

## Key Findings

### Predictive Power of Features
The analysis revealed that certain features are particularly influential in predicting term deposit subscriptions:
- **Previous Campaign Outcome**: The outcome of previous marketing campaigns (poutcome) is one of the strongest predictors.
- **Economic Indicators**: Variables like the euribor 3-month rate and employment variation rate also play a critical role in influencing subscription decisions.
- **Pdays**: Whether a client was contacted in a previous campaign (and how recently) significantly affects the likelihood of a successful subscription.

### Model Performance
- **Logistic Regression** provided a balanced approach, showing strong performance with interpretable coefficients.
- **Decision Trees** were effective but prone to overfitting, especially on the training data, suggesting the need for more regularization.
- **SVM** (Support Vector Machine) showed robust performance but at the cost of higher computational resources.
- **K-Nearest Neighbors (KNN)** also performed well but was less interpretable compared to Logistic Regression and Decision Trees.

### Practical Applications
- The models and insights generated can assist the bank in targeting clients more likely to subscribe to a term deposit, thereby improving the efficiency of their marketing campaigns.
- Understanding the most important features allows the bank to refine their client segmentation and marketing messages, focusing on the factors that most strongly influence subscription decisions.

### Future Recommendations
- Incorporate additional features that capture client behavior over time, such as changes in their financial status or previous interactions with the bank.
- Explore more advanced ensemble methods like Random Forests or Gradient Boosting to potentially improve predictive accuracy.
- Regularly update the models with new data to capture evolving client behavior and market conditions.

## View Notebook
You can view the Jupyter notebook [directly on GitHub](prompt_III.ipynb) or via this [nbviewer link](https://nbviewer.org/github/monomial/ucbai-pa-iii/blob/main/prompt_III.ipynb).

## Getting Started

### Prerequisites
Before running this project, you need to have Python installed on your system along with the following libraries:
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

### Installation
Clone this repository to your local machine:
```bash
git clone https://github.com/monomial/ucbai-pa-iii.git
cd ucbai-pa-iii
```

### Running the Project
Open the Jupyter notebook in your preferred environment and run the cells sequentially to reproduce the analysis and models.

```bash
jupyter notebook prompt_III.ipynb
```
