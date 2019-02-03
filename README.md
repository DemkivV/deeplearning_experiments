# Deep Learning Portfolio
Collection of various deep learning experiments with details and demos of results. (Work in progress.)

1. [Autoencoders](#autoencoders)

    1.1 [Identity](#identity)

    1.2 [Denoising](#denoising)

    1.3 [Super-Resolution](#super-resolution)

# Autoencoders
## Identity
Convolutional identity autoencoder. It could be useful to evaluate the precision of feature representations and find the right spot between undercomplete and overcomplete representations to avoid overtraining and underperformance for the given data domain.

### Details
* *Training details*:
  * *Training objective*: Reproduction of input after encoding it into a feature map.
  * *Loss function*: Mean squared error.
  * *Optimizer*: Adam.
* *I/O*:
  * *Input*: (28, 28, 1) grayscale images of digits (MNIST dataset).
  * *Ground truth*: Same as input.

### Results
* *Content*: Validation results over the course of 20 training epochs.
* *Layout*:
  * *Top row*: Input (= ground truth).
  * *Bottom row*: Prediction.



![Animated ](autoencoder/identity/mnist/conv_autoencoder_20.gif)



## Denoising
Convolutional autoencoder. It removes noise from the input image. This can be useful e.g. for photos taken in the dark.

### Details
* *Training details*:
  * *Training objective*: Reproduction of input after encoding it into a feature map.
  * *Loss function*: Mean squared error.
  * *Optimizer*: Adam.
* *I/O*:
  * *Input*: (28, 28, 1) grayscale images of digits (MNIST dataset).
    * *Augmentation*: With noise (preprocessed once before the training).
  * *Ground truth*: Unaugmented input.

### Results
* *Content*: Validation results over the course of 20 training epochs.
* *Layout*:
  * *Top row*: Input.
  * *Mid row*: Prediction.
  * *Top row*: Ground truth.



![Animated ](autoencoder/denoiser/mnist/conv_autoencoder_20.gif)



## Super-Resolution
Convolutional autoencoder. It quadruples the resolution of the input image. This can be useful e.g. for supersampling, but also more efficient rendering at a lower original resolution.

### Details
* *Training details*:
  * *Training objective*: Upscale the input image to the quadruple resolution (double width and height).
  * *Loss function*: Mean squared error.
  * *Optimizer*: Adam.
* *I/O*:
  * *Input*: (14, 14, 1) grayscale images of digits (MNIST dataset), downscaled from original size (28, 28, 1).
    * *Augmentation*: Noise (preprocessed once before the training).
  * *Ground truth*: (28, 28, 1) original resolution of input image.

### Results
* *Content*: Validation results over the course of 20 training epochs.
* *Layout*:
  * *Top row*: Input.
  * *Mid row*: Prediction.
  * *Top row*: Ground truth.



![Animated ](autoencoder/super-resolution/mnist/conv_autoencoder_20.gif)


