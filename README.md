# Magic_nn
Program which used neural network to predict data from MAGIC Gamma Telescope.

![alt text](https://github.com/alexzedev/Magic_nn/blob/main/magic_nn_screen.png?raw=true)

The data are MC generated (see below) to simulate registration of high energy gamma particles in a ground-based atmospheric Cherenkov gamma telescope using the imaging technique. Cherenkov gamma telescope observes high energy gamma rays, taking advantage of the radiation emitted by charged particles produced inside the electromagnetic showers initiated by the gammas, and developing in the atmosphere. This Cherenkov radiation (of visible to UV wavelengths) leaks through the atmosphere and gets recorded in the detector, allowing reconstruction of the shower parameters. The available information consists of pulses left by the incoming Cherenkov photons on the photomultiplier tubes, arranged in a plane, the camera. Depending on the energy of the primary gamma, a total of few hundreds to some 10000 Cherenkov photons get collected, in patterns (called the shower image), allowing to discriminate statistically those caused by primary gammas (signal) from the images of hadronic showers initiated by cosmic rays in the upper atmosphere (background).

Typically, the image of a shower after some pre-processing is an elongated cluster. Its long axis is oriented towards the camera center if the shower axis is parallel to the telescope's optical axis, i.e. if the telescope axis is directed towards a point source. A principal component analysis is performed in the camera plane, which results in a correlation axis and defines an ellipse. If the depositions were distributed as a bivariate Gaussian, this would be an equidensity ellipse. The characteristic parameters of this ellipse (often called Hillas parameters) are among the image parameters that can be used for discrimination. The energy depositions are typically asymmetric along the major axis, and this asymmetry can also be used in discrimination. There are, in addition, further discriminating characteristics, like the extent of the cluster in the image plane, or the total sum of depositions.

Neural Networks used in this algorithm extract identifying features from data, lacking pre-programmed understanding. Network components include neurons, connections, weights, biases, propagation functions, and a learning rule. Neurons receive inputs, governed by thresholds and activation functions. Connections involve weights and biases regulating information transfer. Learning, adjusting weights and biases, occurs in three stages: input computation, output generation, and iterative refinement enhancing the network’s proficiency in diverse tasks.

![alt text](https://github.com/alexzedev/Magic_nn/blob/main/Neural.jpg?raw=true)


This Neural network is based on two types of activation functions. RELU and Sigmoid.

RELU Function 
It Stands for Rectified linear unit. It is the most widely used activation function. Chiefly implemented in hidden layers of Neural network.
Equation :- A(x) = max(0,x). It gives an output x if x is positive and 0 otherwise.
Value Range :- [0, inf)
Nature :- non-linear, which means we can easily backpropagate the errors and have multiple layers of neurons being activated by the ReLU function.
Uses :- ReLu is less computationally expensive than tanh and sigmoid because it involves simpler mathematical operations. At a time only a few neurons are activated making the network sparse making it efficient and easy for computation.

Sigmoid Function
It is a function which is plotted as ‘S’ shaped graph.
Equation : A = 1/(1 + e-x)
Nature : Non-linear. Notice that X values lies between -2 to 2, Y values are very steep. This means, small changes in x would also bring about large changes in the value of Y.
Value Range : 0 to 1
Uses : Usually used in output layer of a binary classification, where result is either 0 or 1, as value for sigmoid function lies between 0 and 1 only so, result can be predicted easily to be 1 if value is greater than 0.5 and 0 otherwise.

![alt text](https://github.com/alexzedev/Magic_nn/blob/main/relu_sigm.png?raw=true)

And used Adam Optimizer Algorithm
Adam(Adaptive Moment Estimation) is an adaptive optimization algorithm that was created specifically for deep neural network training. It can be viewed as a fusion of momentum-based stochastic gradient descent and RMSprop. It scales the learning rate using squared gradients, similar to RMSprop, and leverages momentum by using the gradient’s moving average rather than the gradient itself, similar to SGD with momentum.
