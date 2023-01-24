**Optimize TensorFlow Models For Deployment with TensorRT**


Optimize Tensorflow models using the TensorFlow integration of NVIDIA's TensorRT (TF-TRT)

Use TF-TRT to optimize several deep learning models at FP32, FP16, and INT8 precision   

Observe how tuning TF-TRT parameters affects performance and inference throughput

 TensorRT is a library that facilitates high-performance inference on NVIDIA graphics processing units (GPUs).
 It is designed to work in a complementary fashion with training frameworks such as TensorFlow,Caffe, PyTorch, MXNet, etc.
 
 
Typically, model training is performed using 32-bit floating point mathematics. Due to the backpropagation algorithm and weights updates, this high precision is necessary to allow for model convergence. Once trained, inference could be done in reduced precision (e.g. FP16) as the neural network architecture only requires a feed-forward network. lowering numerical precision allow for Smaller model,Faster inferencing time Lower memory requirements Increased throughput


If your existing TensorFlow model contains a non-supported layer or operation, can TensorRT still be used to accelerate inference
When optimizing a TensorFlow model, TF-TRT can optimize either a  subgraph or the entire graph definition. This capability allows the  optimization procedure to be applied to the graph where possible and  skip the non-supported graph segments. As a result, if the existing  model contains a non-supported layer or operation, TensorFlow can still  optimize the graph.



What is the extra step required for TF-TRT INT8 quantization?
Calibration is a step performed by TF-TRT when deciding suitable scale factors for 8-bit inference. The calibration process can be used to examine the true range of distribution of activations. In order to perform INT8 inference, FP32 activation tensors and weights need to be quantized. In order to represent 32-bit floating point values and INT 8-bit quantized values, TensorRT needs to understand the dynamic range of each activation tensor. The dynamic range is used to determine the appropriate quantization scale.


 These graph optimizations do not change the underlying computation in the graph; instead, they look to restructure the graph to perform the operations much faster and more efficiently.
