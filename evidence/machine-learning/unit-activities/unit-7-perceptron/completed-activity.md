# Unit 7: Perceptron Activities — Completed Activity

**Module:** Machine Learning  
**Unit:** 7 — Introduction to Artificial Neural Networks  
**Evidence:** Three university-provided Jupyter notebooks, executed outputs and screenshots

## 1. Aim and approach

I worked through three notebooks to understand how a perceptron combines inputs with weights, how a simple model can be trained on the AND operation, and why a multilayer network is needed for a more complicated pattern such as XOR. I ran the supplied examples and made controlled changes in Exercises 1 and 2. For Exercise 3, I recorded the original multilayer training and final outputs rather than claiming a separate parameter experiment.

## 2. Exercise 1 — Simple perceptron

The notebook used two inputs, `[45, 25]`, a weighted sum and a step function. I compared positive and negative values for the first weight, leaving the inputs unchanged.

| Measure | Original | Modified |
|---|---:|---:|
| Inputs | `[45, 25]` | `[45, 25]` |
| Weights | `[0.7, 0.1]` | `[-0.7, 0.1]` |
| Weighted sum | `34.0` | `-29.0` |
| Step-function output | `1` | `0` |

Changing the first weight from positive to negative moved the weighted sum below the activation threshold, changing the output from 1 to 0. **These weights were chosen manually; this example did not train the perceptron.**

**Evidence:** [Original weights and output](screenshots/ex1-simple-original.png) · [Modified weights and output](screenshots/ex1-simple-modified.png)

## 3. Exercise 2 — Perceptron learning the AND operator

The AND operator produces an output of 1 only when both inputs are 1. I initialised the weights to `[0.0, 0.0]`, ran the notebook's training routine and checked each of the four examples. I then reset the weights and changed the learning rate from `0.1` to `0.2`.

| Input | Expected output | Output with learning rate 0.1 | Output with learning rate 0.2 |
|---|---:|---:|---:|
| `[0, 0]` | 0 | 0 | 0 |
| `[0, 1]` | 0 | 0 | 0 |
| `[1, 0]` | 0 | 0 | 0 |
| `[1, 1]` | 1 | 1 | 1 |

| Measure | Original | Modified |
|---|---|---|
| Learning rate | `0.1` | `0.2` |
| Initial weights | `[0.0, 0.0]` | `[0.0, 0.0]` |
| Final weights | `[0.5, 0.5]` | `[0.6, 0.6]` |
| Training classifications | All four correct | All four correct |

The higher learning rate resulted in different final weights, but both settings classified the AND examples correctly. I **did not measure the number of training passes**, so I cannot conclude that one setting trained faster. The exercise also uses a simplified update rule and only a very small training dataset.

**Evidence:** [Initial settings](screenshots/ex2-and-initial.png) · [Training updates](screenshots/ex2-and-training.png) · [Original AND outputs](screenshots/ex2-and-original.png) · [Modified learning-rate outputs](screenshots/ex2-and-modified.png)

## 4. Exercise 3 — Multilayer perceptron and XOR

The third notebook introduced two input values, a hidden layer with three neurons and one output neuron. Its displayed weight matrices had shapes `(2, 3)` and `(3, 1)`. It used the sigmoid activation function and a longer training example with `400000` epochs and `learning_rate = 0.6`.

The training output showed the error decreasing over time. After training, the network returned the expected XOR decisions:

| Input | Expected XOR output | Recorded output |
|---|---:|---:|
| `[0, 0]` | 0 | 0 |
| `[0, 1]` | 1 | 1 |
| `[1, 0]` | 1 | 1 |
| `[1, 1]` | 0 | 0 |

This illustrated why a hidden layer is valuable: unlike AND, XOR cannot be separated by one straight decision boundary. I recorded the completed notebook's architecture, decreasing training error and predictions. I did not perform a controlled comparison of learning rates or epoch counts for this third exercise.

**Evidence:** [Weights and layer dimensions](screenshots/ex3-multilayer-architecture.png) · [Training error output](screenshots/ex3-multilayer-training.png) · [XOR classification results](screenshots/ex3-multilayer-xor-results.png)

## 5. What the three exercises demonstrated

Together, the notebooks showed a progression from manually adjusting weights, to training a perceptron on a simple logical rule, to using hidden neurons to learn a nonlinear pattern. They helped me connect inputs, weights, learning rates, activation functions and predictions with the wider topic of artificial neural networks.

**Limitations:** The examples use four logical input combinations rather than realistic datasets. Correct classification of these examples does not establish performance on unseen or more complex data. Some illustrations in the supplied notebook did not load, and the multilayer notebook included an intermediate matrix-shape issue; I relied on successfully executed training and final classification outputs for the evidence presented here.

## 6. Learning outcomes

These activities support my understanding of applying machine-learning techniques and their limitations (particularly **LO2 and LO3** as mapped in my portfolio). Recording both successful outputs and limitations is also relevant to responsible and transparent reporting of machine-learning results.

**Source:** University of Essex Online (2026), *Machine Learning*, Unit 7 perceptron notebook activities (module-provided materials).
