Context and Motivation    

Ordinal classification is the task of assigning observations to a set of categories in which the labels have a natural hierarchy. A common approach is to treat this problem as regression where the prediction is on a continuous scale. This can add insight where an ordinal variable is present but a continuous measure is desired. For example, predicting the grade a student will receive on a test can be instead treated as predicting the grade percentage out of 100.

In cases where there is no ground truth continuous measure, a proxy can be used. However, when this occurs there is an observable trend in which models trained on the ordinal binned labels will take more complexity than the underlying continuous measure. In addition, models trained on the binned labels will overfit much less quickly as model complexity increases than models trained on a continuous measure.

Goals

These observations have been the focus of McKade’s thesis research under Dr. Wisler’s supervision. For the deep learning final project, we would like to extend these results, which focus on the modeling strategy of gradient boosting, to neural networks. The complexity of the model in this case would be represented by the size of the network, either in terms of number of layers, size of hidden layers, or a meaningful concatenation of the two.

Data

The data for the project is based on energy usage in steel production from the UCI ML repository, the URL for which can be found at the end of the proposal. This dataset has been used in previous studies regarding machine learning-based prediction and many of the same preprocessing steps would be followed. It contains approximately 35,000 observations as well as 9 input features which are a mixture of categorical and continuous. The input features would need to be dummy encoded and/or scaled appropriately and some feature selection and/or engineering would be required.

Methods

In general, the experimental methods involve binning the continuous response of energy usage based on its distribution into five categories to represent ordinal labels. For different levels of complexity, a neural network would be used to predict the labels on a continuous scale. Therefore, this is a supervised regression model even though the output feature is originally ordinal. Using the residuals from this neural network model and the synthetic ordinal labels, a simple linear regression model is built to predict the original continuous measure. The task is to observe trends across complexity and ultimately to identify a range for which complexity should be controlled for binned models in order to achieve optimal performance without overfitting. 
These results would be compared to the previous findings involving gradient boosting. In addition, previous research using this same dataset was performed using several machine learning methods including random forest and CART. The RMSE achieved by these models will be used as a benchmark for comparing performance of the neural network model and SLR. This framework will also include a monte carlo simulation where the data is randomly partitioned for each simulation.

In summary, using the steel energy usage dataset, we will create an ordinal classification task for a neural network model as well as an SLR, compare performance across complexity for both the classification and regression tasks respectively, and establish a pattern of optimization such that the ordinal classification model is optimized on a validation set without overfitting.
# STAT-6810
