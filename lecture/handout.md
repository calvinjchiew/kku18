# Summary of Key Concepts

## Model Fit
- In statistical modelling, we want to estimate f in Y = f(X) + e, where Y is the response (outcome), X is a set of features (predictors), and e is the error.
- To prevent overfitting, we split the data into training and testing sets. We develop the model on the training set, then evaluate its performance on the testing set.
- We choose an error (loss) function appropriate for the prediction task, eg. mean squared error (sum of residuals squared divided by sample size) for regression (continuous Y), sum of misclassifications for classification (categorical Y).

## Random Forest
- Random forest is an ensemble method combining multiple decision trees to improve prediction accuracy.
- A decision tree is essentially a series of branching rules based on the predictors.
- To build a classification tree, we use recursive binary splitting, and aim to increase node purity with each split. A stopping criterion is specified, eg. minimum node size, maximum tree depth.
- At each branching point, only a random subset of all predictors are considered as potential split candidates. This is done to decorrelate the trees.

## Support Vector Machine
- In SVM, we want to draw a (p-1)-dimensional separating hyperplane between the classes, where p is the number of predictors.
- If multiple hyperplanes are possible, we choose the one with the largest margin.
- To make the separating hyperplane more robust to outliers, we tolerate some observations on the wrong side of the hyperplane. The tuning parameter `C` controls the amount of slack given. A smaller `C` results in a softer margin.
- Given a set of data points that are not linearly separable, we can use a non-linear kernel function (eg. radial basis function, RBF) to project them onto a higher-dimensional space and draw the separating hyperplane in that space. 

## Cross-validation
- Cross-validation is a resampling method that can be used to tune parameters of a model.
- In k-fold CV, we split the training data into k folds, take 1 fold to validate and remaining k-1 folds to train. Then calculate the chosen performance metric, repeat k times and average the result.

## Others
- A Receiver Operating Characteristic (ROC) curve is a plot of true positive rate (sensitivity) against false positive rate. An ideal classifier will produce a curve that hugs the top left-hand corner, maximizing the area under the curve (AUC). Random guessing is equivalent to AUC of 0.5.
- When dealing with imbalanced data, we can under- or over-sample to create balanced datasets, or apply class weights.
