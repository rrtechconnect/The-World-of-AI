
**1. What do you think applying this filter to a grayscale image will do?**
[0  1  1  0, 1  3  3  1,-1 -3 -3 -1,0 -1 -1  0]
 
  It will detect Horizontal edges. There is a high difference between the values in the top part from those in the bottom part of the matrix. When convolving this filter on a grayscale image, the horizontal edges will be detected.
 
**2.Suppose your input is a 128 by 128 grayscale image, and you are not using a convolutional network. If the first hidden layer has 256 neurons, each one fully connected to the input, how many parameters does this hidden layer have (including the bias parameters)?**

The number of inputs for each unit is 128×128, since the input image is grayscale, so we need 128×128×256 parameters for the weights and 256 parameters for the bias thus 128×128×256+256= 4194560.

**3.Suppose your input is a 300 by 300 color (RGB) image, and you use a convolutional layer with 100 filters that are each 5x5. How many parameters does this hidden layer have (including the bias parameters)?**

25×3=75 weights and 1 bias per filter. Given that you have 100 filters, you get 7,600 parameters for this layer.

**4.You have an input volume that is 127×127×16, and convolve it with 32 filters of 5×5, using a stride of 2 and no padding. What is the output volume?
using the formula **

62x62x32

**5. You have an input volume that is 31x31x32, and pad it using “pad=1”. What is the dimension of the resulting volume (after padding)?**

33x33x32
Yes, if the padding is 1 you add 2 to the height dimension and 2 to the width dimension.

**6.You have a volume that is 121×121×32, and convolve it with 32 filters of  5×5, and a stride of 1. You want to use a "same" convolution. What is the padding?**
   
   2
   
**7.You have an input volume that is 128x128x12, and apply max pooling with a stride of 4 and a filter size of 4. What is the output volume?**

32x32x12

**8.Because pooling layers do not have parameters, they do not affect the backpropagation (derivatives) calculation.**

False

Everything that influences the loss should appear in the backpropagation because we are computing derivatives. In fact, pooling layers modify the input by choosing one value out of several values in their input volume. Also, to compute derivatives for the layers that have parameters (Convolutions, Fully-Connected), we still need to backpropagate the gradient through the Pooling layers.

**9.Which of the following are true about convolutional layers? (Check all that apply)**

   Convolutional layers provide sparcity of connections

   It allows a feature detector to be used in multiple locations throughtout the whole input volume
   Yes, since convolution involves sliding the filter throughout the whole input volume the feature detector is computed over all the volume.
   Yes, this happens since the next activation layer depends only on a small number of activations from the previous layer.

**10. The sparsity of connections and weight sharing are mechanisms that allow us to use fewer parameters in a convolutional layer making it possible to train a network with smaller training sets. True/False?**

True

weight sharing reduces significantly the number of parameters in a neural network, and sparsity of connections allows us to use a smaller number of inputs thus reducing even further the number of parameters.
