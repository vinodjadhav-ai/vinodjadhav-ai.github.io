# Unit 7: Perceptron Activities — Learning Reflection

## What?

I worked through three notebooks covering a simple perceptron, an AND operator and a multilayer perceptron. In the first exercise, changing a weight from `0.7` to `-0.7` changed the weighted sum from `34` to `-29` and switched the output from 1 to 0. In the second, I trained the AND perceptron and compared learning rates of `0.1` and `0.2`. Both produced the correct four outputs, although their final weights differed. In the final notebook, I examined the hidden-layer architecture, falling training error and correct XOR results.

## So What?

Before these activities, I understood a neural network mainly as something that learns from examples, but I was not clear about what the weights and activation functions actually did. Running the calculations helped me see that the output depends on the weighted inputs and that training changes those weights. The XOR example was especially helpful because it showed why adding a hidden layer can solve a pattern that a single standard perceptron cannot. I also learned not to assume a higher learning rate is automatically better: the two AND experiments had different weights but the same classifications.

## Now What?

I want to connect these small examples to the CNN I used in my Fashion-MNIST project, particularly how networks learn useful features and how I should evaluate their results. In future experiments I would record training passes, use a test set where appropriate and compare settings systematically instead of judging learning only from the final outputs.
