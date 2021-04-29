Recent advances in the estimation of heterogenous causal effects build on supervised machine learning methods that have  been traditionally used for predictive tasks. Assuming unconfoundedness, we estimate and compare 4 different models. Each model in implemeted in a dedicated notebook.  


Project overview:

**Models 1 and 2 : Double Machine Learning causal effect estimation**

Under the assumption of unconfoundedness, it is possible to estimate unbiased causal effects of a policy intervention (in our case a Bilateral Investment Agreement) by taking in consideration selection into treatment. Double Machine Learning models consists of 3 main steps:

1. Prediction of the presence of a BIT between two countries using a set of socio economic characterisitcs
2. Prediction of the FDI flows between the two countries using a set of sociao economic characteristics
3. Estimation of the causal effect of the BIT on FDI flows, making use of the difference between the predicted values of the first two steps and their respective observed values.

For **Model 1** and **Model 2**, the first two steps are identical, and estimated using a RandomForestClassifier and a RandomForestRegression model, respectively. The two models differ in the third step:


* *Model 1: Parametric estimation:* the third step is estimated using a traditional linear regression model.



* *Model 2: Non-parametric estimation:* the third step is estimated using a Causal Random Forest




**Models 3 and 4 : Doubly robust  causal effect estimation**

Doubly robust methods different from the estimation techniques used in model 1 and 2  in that the prediction of the outcome of interest also uses the treatment variable. The technique used for step 3 of models 3 and 4 therefore match those of models 1 and 2, but they use different predicted values for step 2, and therefore will yield different results.


All estimations are made using the **econoML** library:
* https://econml.azurewebsites.net/reference.html
* https://econml.azurewebsites.net/spec/estimation.html
