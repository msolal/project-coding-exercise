# MSc Research Project - Coding Exercise

## Task

1. Download this csv file: https://github.com/anndvision/data/blob/main/jasmin/four_outputs_liqcf_pacific.csv
2. Use the variables {tot_aod, RH700, RH850, w500, whoi_sst} as you input variables X
3. Use the variable {cod} as your target variable Y
4. Create a function that yields a random train, validation, and test split of the data
5. Create a neural network that can regress the outcome Y from the covariates X
6. Generate a random train, valid, and test split
7. Update the model parameters using your training split, and stop training when the model stops improving on the validation set.
8. Evaluate the pearson correlation R^2 between the model predictions and the labels Y using the test set 
9. Repeat step 5 ten times and report the average and standard error of the test set R^2 score
10. Email a link to a github repo containing your implementation and provide a readme explaining how we can replicate your results. You can use whatever machine learning framework you like, but please list each software package and version you use.
