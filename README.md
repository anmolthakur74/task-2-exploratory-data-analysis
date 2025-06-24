# Task 2: Exploratory Data Analysis (EDA)

This repository contains my submission for Task 2 of the AI & ML Internship. The goal of this task was to explore the Titanic dataset using statistics and visualizations to uncover patterns, relationships, and outliers before moving on to machine learning.

## Objective  
Understand data using statistics and visualizations.

## Files Included

1. **Titanic-Dataset.csv** – The raw dataset used for EDA  
2. **titanic_EDA.ipynb** – Jupyter Notebook containing all the analysis and visualizations  
3. **screenshots/** – Folder storing visuals generated during EDA  
4. **README.md** – This documentation

## What I Did

1. The study started by analyzing the dataset's structure via describe(), which helped to outline the key statistical features of every attribute and pointed out any missing values and data types. I employed mode() to identify the most frequently occurring values, which was particularly useful for skewed variables like Age and Fare.

2. To understand how data values were distributed, I plotted histograms for all numerical columns and saved the visual as titanic_numeric_plots.png. These plots made it easy to detect skewness and spot concentration zones across features. Boxplots in the same image were used to visualize outliers—Fare had a few extreme values far above the average, while the Age column included passengers aged 70 and above that clearly stood out.

3. I constructed a heatmap of the correlation matrix comparing all attributes and saved it as correlation_matrix.png. This gave me a quick visual on the correlations of attributes. I can see there is a strong negative correlation on Pclass and Survived and a slight positive correlation on Fare and Survived, I used a pairplot to better show these relationships and saved it as pairplots.png. The pairplot allowed me to see the interactions of features grouped by survival and it also showed how the features such as Fare, Age, Pclass and Survived are all in some way related. Overall I am glad I did this analysis because I was able to spot obvious patterns. Gender and passenger class had a considerable impact on survival rates. Female passengers were more likely to survive, and those traveling in first class had considerably better odds than those in lower classes. Age was a crucial factor—young individuals and children had higher survival rates than older adults. 

4. Some anomalies also stood out. A few passengers paid extremely high fares, exceeding 500, and a small number of passengers had very high ages relative to the rest of the dataset. These outliers will be important to address during preprocessing.

5. The visualizations highlighted a number of feature-level insights. The Sex feature was a strong predictor of survival, Pclass was also significant. Most of the passengers had either a value of 0 (traveled alone) or a value of 1 (traveled with run family); thus, we didn't see much variability for SibSp and Parch. Regarding Fare, it was highly right skewed and so we may need to run our modelling with a log transformation if possible.

### Inferences

Overall, it was obvious from analysis and exploration that some features clearly had greater predictive capability than others. Sex, Pclass, and Fare stood out visually and statistically and should be maximized during feature selection when choosing features in any classification model. The features listed above are most likely to contain meaningful signals for training a model to predict survival. 

While visual means aided in confirming obvious patterns, it also revealed limitations in features relative to my prior expectations. For instance, both SibSp and Parch features exhibited a generally low level of variance across the majority of passengers. This means I am less likely to use them unless I engineer features differently or create a new feature with family size.

The correlation analysis also assisted with checking for multicollinearity. Multicollinearity does not seem to be a big factor since most of the features are not strongly correlated with each other so I can include several features without placing a risk on the stability of the coefficients in my model.

Another observation was that there was skewness and outliers in the distribution of Fare and Age. This suggests that preprocessing methods such as outlier handling and feature scaling will be imperative. I think we will also consider log transforming or using a robust scaler with some features before fitting to model.

## Tools & Libraries Used

1. Python 3.12  
2. pandas, numpy – for data analysis  
3. seaborn, matplotlib – for data visualization

## What I Learned

This task emphasized how important it is to conduct EDA before even thinking about model development. It was beneficial to visualize the data to identify skewed distributions, outliers, and relationships between different features. Furthermore, I have become more comfortable using seaborn's plotting functions, and interpreting other characteristics of distributions and relationships, rather than just relying on the mean and standard deviation. These observations will be beneficial in the preprocessing and feature engineering steps of future assignments.

## How to Run This Project

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/task-2-exploratory-data-analysis.git
   cd task-2-exploratory-data-analysis

2. ```bash
   pip install pandas numpy matplotlib seaborn plotly

3. jupyter notebook titanic_EDA.ipynb

## Author
Anmol Thakur
GitHub: anmolthakur74
