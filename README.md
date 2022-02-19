# MSc Research Project - Coding Exercise

## Task

1. Download this csv file: https://github.com/anndvision/data/blob/main/jasmin/four_outputs_liqcf_pacific.csv
2. Use the variables {tot_aod, RH700, RH850, w500, whoi_sst} as you input variables X
3. Use the variable {cod} as your target variable Y
4. Create a function that yields a random train, validation, and test split of the data
5. Create a neural network that can regress the outcome Y from the covariates X
6. Generate a random train, valid, and test split
    1. Update the model parameters using your training split, and stop training when the model stops improving on the validation set.
    2. Evaluate the pearson correlation R^2 between the model predictions and the labels Y using the test set 
7. Repeat step 5 ten times and report the average and standard error of the test set R^2 score
8. Email a link to a github repo containing your implementation and provide a readme explaining how we can replicate your results. You can use whatever machine learning framework you like, but please list each software package and version you use.

## Methods

We propose 3 different models to regress the outcome Y from the covariates X:
1. Linear regression
2. Non-linear regresssion using polynomial basis expansion
3. Multi Layer Perceptron with 1 or 2 hidden layers, and relu activation

To evaluate the performance of these models, we output the Pearson Correlation R^2, which is a measure of linear correlation between two sets of data X and Y. This coefficient ranges from 0 to 1. A value of 1 indicates perfect linear correlation, i.e. the data points from X and Y lie exactly on a line. Values closer to 0 indicate weaker linear correlation. 

This work was done using python (version 3.9.7), using implementations from the scikit-learn library (version 1.0.2). We have also used other python libraries including pandas (version 1.4.0), numpy (version 1.21.2) and pathlib. 

To replicate these results, run the jupyter notebook that is in this repository. For the code to run smoothly, one should have the data file saved in the same directory or adjust the file path in the 'Load Dataset' section appropriately. 

## Results

The results we obtained are unfortunately quite bad (with a Pearson correlation coefficient around 0.25 at best), and we could probably improve those by using more complex models or better tuning the models we used. Unfortunately, because the training times for the models we implemented are already quite long (especially for the MLP models), we were not able to run further experiments to improve our results.

Given more time, we would plot learning curves to better understand if our model is overfitting or underfitting. We would adjust the learning rate and the stopping criterion. We could also consider building MLPs with more hidden layers in case of underfitting. In case of overfitting, we would go back to simpler models, maybe Bayesian Regression for example. 

| Network Architecture                  | Mean Pearson Correlation for 10 tests |
| ---                                   | ------                                |
| Linear Regression                     | 0.1767                                |
| Polynomial Basis Expansion (degree 5) | 0.2412                                |
| MLP with 1 hidden layer               | 0.2467                                |
| MLP with 2 hidden layers              | 0.2512                                |
