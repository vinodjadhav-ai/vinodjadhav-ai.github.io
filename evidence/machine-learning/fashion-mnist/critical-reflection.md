# Fashion-MNIST — Critical Reflection

## What?
For my individual assessment, I compared Logistic Regression with a convolutional neural network on the Fashion-MNIST clothing-image dataset. I used the same training and validation examples for both models and kept a separate test set for evaluation. I looked at accuracy, error patterns, training curves and Grad-CAM examples rather than only checking whether the code ran.

## So What?
At the start I found the CNN architecture more difficult to understand than Logistic Regression. Seeing the test results (84.25% versus 89.77%) helped me appreciate why image-specific layers can be useful, but it also showed me why a simpler baseline matters: the extra complexity should demonstrate a worthwhile improvement. My Logistic Regression run also showed a convergence warning, reminding me that training settings can affect the fairness of a comparison.

The recall chart was particularly useful. Shirt recall was only 75.8%, compared with 98.6% for sneakers. This taught me that one headline accuracy figure can hide weaker performance for individual categories. A coat misclassified as a shirt made the issue visible. I initially expected a Grad-CAM heatmap to explain the mistake, but it only shows an approximate pattern of influence; it cannot reliably explain the model's reasoning.

I also noticed that the training and validation curves diverged slightly towards the end. This made me more conscious of overfitting and the value of monitoring performance on data that is not used to adjust the model weights.

## Now What?
In future I would test more than one training/validation split, investigate mistakes in similar clothing categories and try regularisation or tuning while keeping a genuinely held-out test set. I would also evaluate the model with realistic retail photographs before considering deployment. If used in practice, I would start with a small pilot and human review for uncertain classifications. I would avoid claiming that this experiment demonstrates demographic fairness, because the dataset does not contain the relevant information.

This assessment helped me understand that completing a model is not the same as evaluating whether it is dependable, explainable or appropriate for a real application.
