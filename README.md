# Stroke_Prediction
Predicting brain stroke by given features in dataset.

<img src="https://github.com/skp163/California_Housing_FeatureSelection_DimensionalityReduction/blob/main/Assets/Feature%20Selection%20%26%20Dimensionality%20Reduction%20(1).gif" width="800" height="300" />

## Overview
I am using different methods of feature selection and dimensionality reduction on California housing dataset to achive most optimized result. 

### Data Set: <br/>
[sklearn.datasets.fetch_california_housing](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)

***Number of Features : 8*** <br/>
***Sample size: 20640***

### Methods Used:
1. Filterbased Method
    - Using all Features Method
    - Correlation Method
    - Wrapper Based Methods
2. Mutual Information Method
3. PCA


### 1. Filterbased Method

<img src="https://github.com/skp163/California_Housing_FeatureSelection_DimensionalityReduction/blob/main/Assets/Filter_1.png" width="600" height="70" />

        - Using all Features Method:
            Used linear regression for predicting price of the houses in California. In this method
            I have considered all the available features in the model.
            Result:

            |R2_Error |  MSE   |
            |---------|--------|
            | 0.62909 | 0.49887|

        
<img src="https://github.com/skp163/California_Housing_FeatureSelection_DimensionalityReduction/blob/main/Assets/Correlation_Matrix1.png" width="600" height="400" />
        
         - Correlation Method:
           Used Pearson’s Correlation to check how independent varibles are correlated with each other.
           If 2 or more independent features are highly correlated then they can be considered
           as duplicate features and can be dropped. Hence in this case I find 'AveBedrms' and 'AveRooms'
           is highly correlated from the Correlation Matrix. We need to drop one of the. Hence I am
           dropping 'AveRooms'. And I observed little improvement in my r2_error score.

           New reslut is:
            |R2_Error |  MSE   |
            |---------|--------|
            | 0.58185 | 0.55992|

        - Wrapper Based Methods:
           
          In wrapper methods, I try to use a subset of features and train a model using them. 
          Based on the inferences that I draw from the previous model, I decide to add or remove 
          features from the privious subset.
        - Sequential Feature Selection
           New reslut is:
            |R2_Error |  MSE   |
            |---------|--------|
            | 0.55475 | 0.61173|

### 2. Mutual Information Method:
        Mutual Information method is typically information gain methods. Mutual information is 
        calculated between two variables and measures the reduction in uncertainty for one 
        variable given a known value of the other variable.

        New reslut is:
        |R2_Error |  MSE   |
        |---------|--------|
        | 0.58115 | 0.56156|

### 3. PCA
<img src="https://github.com/skp163/California_Housing_FeatureSelection_DimensionalityReduction/blob/main/Assets/Regresor_Line_calibration.gif" width="800" height="350" />

        PCA is an unsupervised linear transformation technique. In this technique, we don't 
        selct features instead we transform the features space intoa lower-dimensional space 
        while preserving maximum variance. The main drawback of this feature is you don’t 
        really know what the new features represent, so although you gain in dimensionality 
        reduction you definitely lose on the interpretability.

        New reslut is:
        |R2_Error |  MSE   |
        |---------|--------|
        | 0.01250 | 1.31898|


        Note : PCA can be used in non-continious feature but it may not be meaningfull in categorical environment.

    


## Reference Link:
https://medium.com/@mayureshrpalav/principal-component-analysis-feature-extraction-technique-3f480d7b9697
https://aegis4048.github.io/mutiple_linear_regression_and_visualization_in_python
https://towardsdatascience.com/feature-selection-techniques-in-regression-model-26878fe0e24e
https://medium.com/mlearning-ai/short-python-code-for-backward-elimination-with-detailed-explanation-52894a9a7880
https://github.com/skp163/California_Housing_FeatureSelection_DimensionalityReduction/tree/main
https://machinelearningmastery.com/feature-selection-for-regression-data/
    