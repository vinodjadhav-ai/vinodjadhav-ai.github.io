# Unit 8 — Gradient Descent: Learning Reflection

## What?

I completed the Unit 8 gradient descent notebook and changed two training parameters to see what happened to the cost. I first ran the original example with 100 iterations and a learning rate of 0.08. I then reduced the iterations to 20 without changing the learning rate. For the final run, I restored 100 iterations and reduced the learning rate to 0.04. I saved screenshots of all three outputs so that I could compare them rather than relying on my memory.

## So what?

Before doing the practical exercise, I understood learning rate and iterations mainly as settings in Python code. The results helped me see what they actually do. In the original run, the last printed cost was about 0.0041. With only 20 iterations, it was about 1.5233. When I used the smaller learning rate of 0.04 over 100 iterations, the cost was about 0.0634. I could see that the model needed enough updates and an appropriate step size to reduce the error. I also learned not to conclude that a larger learning rate is always best, because very large steps can miss the minimum or make training unstable.

Another useful observation was how simple the dataset was: just five points with a clear straight-line pattern. This was helpful for understanding the calculations, but real datasets are not normally so tidy. Noise, unusual values and different relationships could change how successfully the model trains. This connected the exercise to the unit learning outcome about the applicability and challenges of different datasets.

## Now what?

When I train another model, I want to record the original settings first and then change one parameter at a time. I would also like to plot the cost against iterations so that I can see whether training is converging or becoming unstable. For more realistic datasets, I need to pay attention not only to training cost but also to how well the model performs on separate test data.

**Reading follow-up:** I still need to confirm and record my understanding of the assigned Mayo (2017) article separately; these reflections are based on the practical notebook.
