# Genetic-Predictor

In this project I analyzing human genetic data from 𝑁=183 training observations (individuals) sampled across the world. 
The goal is to fit a model that can predict (classify) an individual’s ancestry from their genetic data that has been projected along 𝑝=10 top principal components (proportion of variance explained is 0.2416) that we use as features rather than the raw genetic data, 
as the training would take too long to complete for this project with the raw data.  Specifically, I will perform a penalized (regularized) logistic (multinomial) regression fit using ridge regression, 
with the model parameters obtained by batch gradient descent. The predictions will be based on 𝐾=5 continental ancestries (African, European, East Asian, Oceanian, or Native American). 
Ridge regression will permit you to provide parameter shrinkage (tuning parameter 𝜆≥0) to mitigate overfitting. The tuning parameter 𝜆 will be chosen using five-fold cross validation, 
and the best-fit model parameters will be inferred on the training dataset conditional on an optimal tuning parameter. This trained model will be used to make predictions on new test data points.

Training data

Training data for these observations are given in the attached TrainingData_N183_p10.csv comma-separated file, with individuals labeled on each row (rows 2 through 184), and input features (PC1, PC2, …, PC10) and ancestry label given on the columns (with the first row representing a header for each column).

Test data

Test data are given in the attached TestData_N111_p10.csv comma-separated file, with individuals labeled on each row (rows 2 through 112), and input features (PC1, PC2, …, PC10), and ancestry label given on the columns (with the first row representing a header for each column). There are five individuals with Unknown ancestry, 54 individuals with Mexican ancestry, and 52 individuals with African American ancestry. Each of the five Unknown individuals belong to one of the five ancestries represented in the training set, and each ancestry is represented once in the five Unknown individuals. The Mexican and African American individuals have a range of ancestry proportions based on historical mixing of ancestors of diverse ancestry. 
We will use the class probabilities from logistic (multinomial) regression to predict the ancestry proportion of each of these putatively mixed samples.
