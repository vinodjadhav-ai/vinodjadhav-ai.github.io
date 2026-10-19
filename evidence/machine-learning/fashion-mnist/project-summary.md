# Fashion-MNIST — Individual Project Summary

## Research question
Can a convolutional neural network (CNN) classify Fashion-MNIST clothing images better than a classical Logistic Regression baseline?

## Dataset and fair comparison
The benchmark has 70,000 labelled 28 × 28 grayscale clothing images across ten classes: 60,000 training and 10,000 test images. I normalised pixels to 0–1 and split the original training set into 48,000 training and 12,000 validation images with stratification. The 10,000 test images were held out during development.

- Logistic Regression used flattened 784-pixel input, `C=1.0`, `lbfgs` and `max_iter=200` (the run generated a convergence warning).
- The CNN retained image structure, using Conv2D (32 filters) → pooling → Conv2D (64 filters) → pooling → Flatten → Dense (64) → softmax (10 classes). It used Adam, batch size 128, up to 10 epochs, and early stopping based on validation loss.

## Results

| Classifier | Held-out test accuracy |
| --- | ---: |
| Logistic Regression | 84.25% |
| CNN | 89.77% |

The CNN was **5.52 percentage points** higher on the held-out test set. Its performance was uneven by category: **shirt recall 75.8%** and **sneaker recall 98.6%**. The learning curves show training improving while validation gains level off, suggesting mild overfitting late in training.

## Interpreting predictions
I used Grad-CAM to inspect one correctly classified ankle boot and one coat incorrectly classified as a shirt. The heatmaps offer approximate visual clues to which image regions influence the network, but do not prove the model understood its decision. The supplied `cnn_gradcam_example` image was blank and has **not** been included as evidence; the incorrect-classification example is available.

## Limitations and responsible use
One train/validation split, low-resolution grayscale benchmark images and training convergence limitations restrict conclusions. Fashion-MNIST does not include demographic attributes, so category differences must not be presented as evidence of demographic fairness. Real online retail images are often larger, coloured and more variable. A limited human-reviewed pilot would be preferable to automatic deployment.

## Evidence
- [Executed source notebook](01_ml_vs_dl_comparison.ipynb)
- [Browsable notebook export](01_ml_vs_dl_comparison.html)
- [Presentation slide deck](Fashion_MNIST_Individual_Presentation.pptx)
- [Learning reflection](critical-reflection.md)
- [Training and validation accuracy](screenshots/cnn_accuracy_curve.png)
- [Training and validation loss](screenshots/cnn_loss_curve.png)
- [Category recall](screenshots/cnn_category_recall.png)
- [Incorrect coat/shirt Grad-CAM example](screenshots/cnn_gradcam_incorrect.png)

**Source:** My executed notebook and individual assessment presentation; no new model run was carried out for this portfolio section.
