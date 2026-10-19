# Unit 9 — Learning Reflection: CNN Object Recognition and Ethics

## What?

I worked through the CNN object-recognition notebook using the CIFAR-10 dataset. I initially found the sequence of convolutional layers, pooling and prediction difficult to follow. Running the model and looking at actual images helped me understand what the output represents. The model correctly classified `x_test[16]` as a dog, `x_test[5]` as a frog and `x_test[12]` as a dog.

## So what?

The three successful predictions were encouraging, but the wider evaluation gave a different perspective: the test accuracy was **62.42%**. The training-loss graph also showed that validation loss began increasing while training loss continued decreasing. I learned that checking a few correct images is not enough to judge the reliability of a model, and that overfitting is something to watch for.

The additional reading by **Wall (2019), *Biased and wrong? Facial recognition tech in the dock*** prompted me to think about the ethical implications of image-recognition systems. My CIFAR-10 activity classified objects, not people, so the consequences of an incorrect dog-or-frog prediction were small. A mistake in facial recognition used for policing or security could have a much greater effect on someone's life. I also see why diverse and appropriate training data, privacy safeguards and human review matter. These are connections I drew between the article's topic and my practical experience, rather than findings tested by my CIFAR-10 experiment.

## Now what?

When I evaluate another CNN, I want to compare performance across the full test dataset, check individual classes and examine errors rather than selecting only successful predictions. I would also consider whether the dataset represents the intended real-world use and whether an incorrect prediction could harm someone. This exercise helped me connect a technical task with the responsibilities of developing and using machine-learning systems.

## Reference

Wall, M. (2019) 'Biased and wrong? Facial recognition tech in the dock', *BBC News*. Available at: https://www.bbc.com/news/business-48842750 (Accessed: 19 October 2026).

[Back to completed activity](completed-activity.md)
