# Unit 11: Model Performance Measurement — Learning Reflection

**Module:** Machine Learning  
**Unit:** 11 — Model Selection and Evaluation  
**Activity:** Model Performance Measurement

## What?

I ran the model performance notebook and experimented with two types of evaluation. For the Iris classification example, I changed `test_size` from 0.5 to 0.3 and compared the ROC-AUC results. I also changed some predicted values in a small regression example to see how Mean Absolute Error (MAE) and R² responded. I encountered a warning in the SVM example and adjusted an unnecessary parameter before continuing.

## So What?

The micro-average AUC rose from 0.7277 to 0.7583, but two individual class scores fell slightly. This showed me that an overall improvement does not necessarily mean every class has improved. In the regression example, MAE increased from 0.50 to 0.65 and R² fell from 0.9486 to 0.9226 after I changed the predictions. I found these small experiments more helpful than simply reading metric definitions. They also reminded me to be careful about claiming that a model is better based on one score or one train/test split.

## Now What?

I want to practise evaluating models on separate test data and comparing several metrics rather than relying on a single number. In future projects, I will also look at class-level errors and explain the limitations of my evaluation, especially where model predictions could influence real decisions.
