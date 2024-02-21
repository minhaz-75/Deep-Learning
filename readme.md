
# Understanding-and-Implementing-the-Activation-Function




## How Activation Functions Work in Deep Learning

“In artificial neural networks, each neuron forms a weighted sum of its inputs and passes the resulting scalar value through a function referred to as an activation function.”
—Definition from Wikipedia




![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_13.jpg)

![App Screenshot](https://www.geeksforgeeks.org/wp-content/uploads/33-1-1.png)

![App Screenshot](https://www.ejable.com/wp-content/uploads/2023/11/Activation-function-3.webp)

![App Screenshot](https://d3i71xaburhd42.cloudfront.net/36195b6d4ca86f4476d2f618a966a1560730cb6b/2-Figure2-1.png)


In humans, our brain receives input from the outside world, performs processing on the neuron receiving input and activates the neuron tail to generate required decisions. Similarly, in neural networks, we provide input as images, sounds, numbers, etc., and processing is performed on the artificial neuron, with an algorithm activating the correct final neuron layer to generate results.

## Why do we need activation functions?
An activation function determines if a neuron should be activated or not activated. This implies that it will use some simple mathematical operations to determine if the neuron’s input to the network is relevant or not relevant in the prediction process.

The ability to introduce non-linearity to an artificial neural network and generate output from a collection of input values fed to a layer is the purpose of the activation function

## Types of Activation functions
 
Activation functions can be divided into three types:

1. Linear Activation Function
2. Binary Step Function
3. Non-linear Activation Functions

# Linear Activation Function
The linear activation function, often called the identity activation function, is proportional to the input. The range of the linear activation function will be (-∞ to ∞). The linear activation function simply adds up the weighted total of the inputs and returns the result.

![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_18.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_3.jpg)

## Pros and Cons of Linear Activation Function

1. It is not a binary activation because the linear activation function only delivers a range of activations. We can surely connect a few neurons together, and if there are multiple activations, we can calculate the max (or soft max) based on that.

2. The derivative of this activation function is a constant. That is to say, the gradient is unrelated to the x (input).


# Binary Step Function
A threshold value determines whether a neuron should be activated or not activated in a binary step activation function.

The activation function compares the input value to a threshold value. If the input value is greater than the threshold value, the neuron is activated. It’s disabled if the input value is less than the threshold value, which means its output isn’t sent on to the next or hidden layer.

![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_10.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_11.jpg)

# Pros and Cons of Binary Step Function

1. It cannot provide multi-value outputs — for example, it cannot be used for multi-class classification problems.

2. The step function’s gradient is zero, which makes the back propagation procedure difficult.

# Non-linear Activation Functions
 
The non-linear activation functions are the most-used activation functions. They make it uncomplicated for an artificial neural network model to adapt to a variety of data and to differentiate between the outputs.

Non-linear activation functions allow the stacking of multiple layers of neurons, as the output would now be a non-linear combination of input passed through multiple layers. Any output can be represented as a functional computation output in a neural network.

These activation functions are mainly divided basis on their range and curves. The remainder of this article will outline the major non-linear activiation functions used in neural networks.


![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_11.jpg)

# How to choose a hidden layer Activation Function

![App Screenshot](https://machinelearningmastery.com/wp-content/uploads/2020/12/How-to-Choose-an-Hidden-Layer-Activation-Function.png)

![App Screenshot](https://lnalborczyk.github.io/slides/vendredi_quanti_2021/figures/activation.png)

# 1. Sigmoid
Sigmoid accepts a number as input and returns a number between 0 and 1. It’s simple to use and has all the desirable qualities of activation functions: nonlinearity, continuous differentiation, monotonicity, and a set output range.

This is mainly used in binary classification problems. This sigmoid function gives the probability of an existence of a particular class.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_7.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_2.jpg)

## Pros and Cons of Sigmoid
## Pros
1. It is non-linear in nature. Combinations of this function are also non-linear, and it will give an analogue activation, unlike binary step activation function. It has a smooth gradient too, and It’s good for a classifier type problem.

2. The output of the activation function is always going to be in the range (0,1) compared to (-∞, ∞) of linear activation function. As a result, we’ve defined a range for our activations.
## Cons
1. Sigmoid function gives rise to a problem of “Vanishing gradients” and Sigmoids saturate and kill gradients.

2. Its output isn’t zero centred, and it makes the gradient updates go too far in different directions. The output value is between zero and one, so it makes optimization harder.
3. The network either refuses to learn more or is extremely slow.

# 2.TanH (Hyperbolic Tangent)
 
TanH compress a real-valued number to the range [-1, 1]. It’s non-linear, But it’s different from Sigmoid,and its output is zero-centered. The main advantage of this is that the negative inputs will be mapped strongly to the negative and zero inputs will be mapped to almost zero in the graph of TanH

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_16.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_12.jpg)

## Pros and Cons of TanH
1. TanH also has the vanishing gradient problem, but the gradient is stronger for TanH than sigmoid (derivatives are steeper).

2. TanH is zero-centered, and gradients do not have to move in a specific direction.

# 3. ReLU (Rectified Linear Unit)
ReLU stands for Rectified Linear Unit and is one of the most commonly used activation function in the applications. It’s solved the problem of vanishing gradient because the maximum value of the gradient of ReLU function is one. It also solved the problem of saturating neuron, since the slope is never zero for ReLU function. The range of ReLU is between 0 and infinity.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_1.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_6.jpg)

## Pros and Cons of ReLU
## Pros
1. Since only a certain number of neurons are activated, the ReLU function is far more computationally efficient when compared to the sigmoid and TanH functions.

2. ReLU accelerates the convergence of gradient descent towards the global minimum of the loss function due to its linear, non-saturating property.
## Cons
1. One of its limitations is that it should only be used within hidden layers of an artificial neural network model.

2. Some gradients can be fragile during training.

3. In other words, For activations in the region (x<0) of ReLu, the gradient will be 0 because of which the weights will not get adjusted during descent. That means, those neurons, which go into that state will stop responding to variations in input (simply because the gradient is 0, nothing changes.) This is called the dying ReLu problem.

# 4.Leaky ReLU
Leaky ReLU is an upgraded version of the ReLU activation function to solve the dying ReLU problem, as it has a small positive slope in the negative area. But, the consistency of the benefit across tasks is presently ambiguous.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_19.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_6.jpg)

## Pros and Cons of Leaky ReLU
## Pros
1. The advantages of Leaky ReLU are the same as that of ReLU, in addition to the fact that it does enable back propagation, even for negative input values
## Cons
1. Making minor modification of negative input values, the gradient of the left side of the graph comes out to be a real (non-zero) value. As a result, there would be no more dead neurons in that area.
2. The predictions may not be steady for negative input values.

# 5.ELU (Exponential Linear Units)
ELU is also one of the variations of ReLU which also solves the dead ReLU problem. ELU, just like leaky ReLU also considers negative values by introducing a new alpha parameter and multiplying it will another equation.

ELU is slightly more computationally expensive than leaky ReLU, and it’s very similar to ReLU except negative inputs. They are both in identity function shape for positive inputs.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_8.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_5.jpg)

## Pros and Cons of ELU
## Pros
1. ELU is a strong alternative to ReLU. Different from the ReLU, ELU can produce negative outputs.
## Cons
1. Exponential operations are there in ELU, So it increases the computational time.
2. No learning about the ‘a’ value takes place, and exploding gradient problem.

# 6. Softmax
A combination of many sigmoids is referred to as the Softmax function. It determines relative probability. Similar to the sigmoid activation function, the Softmax function returns the probability of each class/labels. In multi-class classification, softmax activation function is most commonly used for the last layer of the neural network.

The softmax function gives the probability of the current class with respect to others. This means that it also considers the possibility of other classes too.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_9.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_4.png)

## Pros and Cons of Softmax
## Pros
1. It mimics the one encoded label better than the absolute values.
## Cons
1. We would lose information if we used absolute (modulus) values, but the exponential takes care of this on its own.
2. The softmax function should be used for multi-label classification and regression task as well.

# 7. Swish
Swish allows for the propagation of a few numbers of negative weights, whereas ReLU sets all non-positive weights to zero. This is a crucial property that determines the success of non-monotonic smooth activation functions, such as Swish’s, in progressively deep neural networks.

It’s a self-gated activation function created by Google researchers.

 ![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_17.png)

Mathematically, it can be represented as:
![App Screenshot](https://www.kdnuggets.com/wp-content/uploads/activation-functions_14.jpg)

## Pros and Cons of Swish
1. Swish is a smooth activation function that means that it does not suddenly change direction like ReLU does near x equal to zero. Rather, it smoothly bends from 0 towards values < 0 and then upwards again.
2. Non-positive values were zeroed out in ReLU activation function. Negative numbers, on the other hand, may be valuable for detecting patterns in the data. Because of the sparsity, large negative numbers are wiped out, resulting in a win-win situation.
3. The swish activation function being non-monotonous enhances the term of input data and weight to be learnt.
4. Slightly more computationally expensive and More problems with the algorithm will probably arise given time.

# Important Considerations
While choosing the proper activation function, the following problems and issues must be considered:

1. Vanishing gradient is a common problem encountered during neural network training. Like a sigmoid activation function, some activation functions have a small output range (0 to 1). So a huge change in the input of the sigmoid activation function will create a small modification in the output. Therefore, the derivative also becomes small. These activation functions are only used for shallow networks with only a few layers. When these activation functions are applied to a multi-layer network, the gradient may become too small for expected training.

2. Exploding gradients are situations in which massive incorrect gradients build during training, resulting in huge updates to neural network model weights. When there are exploding gradients, an unstable network might form, and training cannot be completed. Due to exploding gradients, the weights’ values can potentially grow to the point where they overflow, resulting in loss in NaN values.

# Final Takeaways
1. All hidden layers generally use the same activation functions. ReLU activation function should only be used in the hidden layer for better results.
2. Sigmoid and TanH activation functions should not be utilized in hidden layers due to the vanishing gradient, since they make the model more susceptible to problems during training.
3. Swish function is used in artificial neural networks having a depth more than 40 layers.
4. Regression problems should use linear activation functions
5. Binary classification problems should use the sigmoid activation function
6. Multiclass classification problems shold use the softmax activation function

# Application function of Deep Learning
![App Screenshot](https://d3i71xaburhd42.cloudfront.net/d37b3c758faa8a998fd1e76be25a3dbe0c86cca2/2-Figure2-1.png)