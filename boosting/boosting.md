
##  ✨ Boosted Trees ✨
- is another form of ensemble technique which uses Decision Tree as base learner
- It is a popular approach
- It differes from Random Forest / Bagged tree in following manner:
        - It uses Data Reweighing strategy than bootstrap sampling while creating the tree
        - The depth of tree is limited(2-3) where as for random forest and Bagged tree model it is as many as required
  
#### Data Reweighing Strategy Using Ada Boost
- Each successive tee pays more attention/ or gives more weight to part of the data which previous models have failed to predict successfully.
- For eg: If in a dataset, the first model was not able to predict the outcome of row one correctly, in that case the next model will add more weight to the row one.

#### Gradient Boosting
- In gradient boosting, after prediction T1, the residual error(y actual vs y predicted) is fit into the next model say T2. This allows T2 to consider the residual term
- Next both T1+T2 is applied against the dataset resulting in a smaller residual as the previous residual was taken into account by model T2.
- This is repeated till we end up with an ensemble of trees
- This also can use any other base learner than decision tree

#### Partial Dependence Plot
- Partial Dependence plot helps to plot the relationship between the target variable and predictors.
- It helps in determining the direction of impact of the predictors on target variables
- However it only allows to explore bivariate relationships
- Also it is expensive interms of computationally
- Depending upon which machine learning experience is used, the partial dependence plot may or may not be supported for the ensembles
