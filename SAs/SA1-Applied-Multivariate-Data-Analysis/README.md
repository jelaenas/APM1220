## **Study title**
An Integrated Multivariate Approach to Analyzing the Physicochemical Properties of Portuguese Vinho Verde Wines

## **Research questions**
The study answers the following research questions:

**Research Question 1 – MANOVA**
*Do red and white wines differ significantly in their overall physicochemical characteristics when several characteristics, specifically total sulfur dioxide, alcohol, residual sugar, and pH, are considered simultaneously?*

**Research Question 2 – PCA**
*Can the 11 physicochemical measurements of wine be summarized using a smaller number of principal components while retaining a substantial proportion of the total variability?*

**Research Question 3 – EFA**
*What underlying latent dimensions or factors explain the relationships among the physicochemical characteristics of wine?*

## **Dataset description**
The dataset contains physicochemical measurements of Portuguese Vinho Verde wines. The red and white datasets were combined into 6,497
observations: 1,599 red and 4,898 white wine samples. No missing values were found. The dataset contains 11 physicochemical variables and a wine-quality score. The wine color variable identifies the samples as red or white. Specifically the dataset contains the following variables:

| Variable | Type | Description |
|---|---|---|
| `fixed acidity` | Continuous | Fixed acidity |
| `volatile acidity` | Continuous | Volatile acidity |
| `citric acid` | Continuous | Citric acid |
| `residual sugar` | Continuous | Residual sugar |
| `chlorides` | Continuous | Chloride concentration |
| `free sulfur dioxide` | Continuous | Free sulfur dioxide |
| `total sulfur dioxide` | Continuous | Total sulfur dioxide |
| `density` | Continuous | Density |
| `pH` | Continuous | pH |
| `sulphates` | Continuous | Sulphates |
| `alcohol` | Continuous | Alcohol concentration |
| `quality` | Integer | Sensory quality score |
| `color` | Categorical | Red or White |

## **Dataset source**
The winequality-red.csv and winequality-white.csv were downloaded from UCI Machine Learning Repository --- Wine Quality:
https://archive.ics.uci.edu/dataset/186/wine+quality 

## **Statistical methods**
For each analysis, the following statistical methods were used:
- Exploratory data analysis: descriptive statistics, histograms, correlation analysis, color-wise distribution plots, IQR outlier checks, and Mahalanobis distance.

- MANOVA: wine color as the independent variable; total sulfur dioxide, alcohol, residual sugar, and pH as dependent variables. Pillai's trace is reported, followed by univariate ANOVAs and eta-squared effect sizes.

- PCA: standardize the 11 physicochemical variables, examine eigenvalues and explained variance, and interpret component loadings.

- EFA: KMO and Bartlett's test, eigenvalue/scree/parallel-analysis factor retention, minres extraction, and Promax rotation.

## **Summary of major findings**
- EDA: it was found that there was strong positive correlation between free and total sulfur dioxide (r = 0.72), negative correlation between density and alcohol (r =-0.69), and positive correlation between residual sugar and density (r = 0.55).

- MANOVA: it was determined that there was a statistically significant difference in the combined selected physicochemical profile between red and white wines:
Pillai's trace = 0.5764, F(4, 6492) = 2208.3011, p < 0.001. In follow-up ANOVAs, total sulfur dioxide had the largest
eta-squared (0.4905); residual sugar (0.1217) and pH (0.1083) also showed notable effect sizes. Alcohol's effect size was very small (0.0011).

- PCA: there were three components retained  with eigenvalues greater than one, explaining 64.36% of standardized variance. PC1, named sulfur dioxide and chemical composition, includes total and free sulfur dioxide, residual sugar, volatile acidity, chlorides, and sulphates. PC2, named density, residual sugar, and alcohol, involves density, residual sugar, and alcohol, while PC3, named acid composition, consists of citric acid, fixed acidity, pH, and volatile acidity.

- EFA: it wad found that the KMO value is 0.405 and density communality is 1.085, which means that the EFA solution must be interpreted cautiously. There were three broad dimensions found in EFA. Factor 1, named acidity–sulfur dioxide dimension, includes fixed acidity, total and free sulfur dioxide, chlorides, volatile acidity, and sulphates. Factor 2, named density–sugar–alcohol dimension, involves density, alcohol, and residual sugar, while Factor 3, named acid composition dimension, consists of citric acid, fixed acidity, pH, and volatile acidity.

## **Software used**
Python in Google Colab. Packages used include pandas, NumPy, Matplotlib, Seaborn, SciPy, statsmodels, scikit-learn, and factor_analyzer.

## **Instructions for reproducing the analysis** 
1. Download winequality-red.csv and winequality-white.csv from the UCI dataset source above or from the data in this repository
2. Download SA1_Wine_Analysis.ipynb found in code branch of  this repository. 
3. Place both CSV files in the same working directory as SA1_Wine_Analysis.ipynb, or update the file paths in the first data-loading cell.
4.  Install the packages used by the notebook if they are not already installed. The notebook already includes an installation command for
factor_analyzer. Other packages may also need to be installed in a fresh environment.
5. Open the notebook in Jupyter Notebook, Kaggle, or Google Colab.
6. Run the notebook cells in order, from data preparation and EDA through MANOVA, PCA, and EFA.
7. Review the generated tables and plots. Note that results may vary slightly due to package versions. Additionally, results will vary for the random seed for the
parallel-analysis simulation.
