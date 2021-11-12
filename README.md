# Abalone Age Prediction

### Problem statement: Find the "age" of Abalone (a kind of sea animal) based on it's bodily feature like sex, height, weight and some more feature.

### Steps:

##### Data Visualization

1. I began by loding the dataset from a .csv file.
2. Next, I added a new column "Age" wich was made by adding 1.5 to "Ring" column.
3. A brief descrbe command gave me full insight of numerical data. I found "height" column had minimum value of 0. Which is Impossible so, later on I treated it as a null value.
4. A quick  histogram of the data gave me a nice idea about the distribution of the data in columns. And Box-Plot for checking for outliers.
5. Then, I checked how the Independent Variablea and  Dependent Variables  are correlated.


##### Feature Engineering

1. I started the FE part by replacing all the "Heights" columns having values 0 with the mean of the column.
2. Dummy Encoded the "sex" column.
3. Next, is I selected a few regression models and tested on the raw data to get a baseline also tested the data with different number of columns. All columns together gave the best result. (Max R2: 0.56 (Linear Regression),  Min R2: 0.53( SGDRegressor) )
4. Next, I scaled the "Input Variable" using a "RobustScaler", due the presence of outliers. (MAX R2: 0.56 (LinearRegression), MIN R2: 0.54 (SGDRegressor))
5. Next, Scaled the "Target Variable".(MAX R2: 0.56 (LinearRegression), MIN R2: 0.52 (SGDRegressor))
6. Normalized the input data using "yeo-johnson". (MAX R2: 0.56 (LinearRegression), MIN R2: 0.54 (SGDRegressor))
7. Tried reducing the dimensionality with PCA. But the best result was with all the 9 values.  (MAX R2: 0.59 (RandomForestRegressor), MIN R2: 0.54 (SGDRegressor))


Since, the RandomForestRegressor tend to perform better after PCA, i choose to go with it and fine tuned it with GridSearchCV. If gave the values (max_depth=10, n_estimators=50).

After applying the hyperparameters the results turned out to be the following on the test data -
  MSE: 0.004970520416112232
  r2: 0.5949145005735985 
  
  
  #### Conclusion
  
  Model can be tested with other algorithims, and it may have performed better.
