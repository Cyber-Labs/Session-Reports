
# Session 7

Paper reading session
Image Net Classification with Deep Convolutional Neural Network by A Krizhevsky - ‎2012
## Resources

Link to paper -- [Image Net Classification with Deep Convolutional Neural Network](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

## Summary

* Convolutional neural networks capacity can be controlled by varying their depth and breadth, and they also make strong and mostly correct assumptional on image data.

* About The Data
	* ImageNet has 15 million high resolution labelled images of 22000 categories and had to be divided into 1000 categories.

* Error Rates
	 * Top 1 Error Rate- This defines the error by comparing the prediction directly to the label.
	* Top 5 Error Rate- Fraction of test images for which the correct label is not among the five labels considered most probable by the model.

* Preprocessing
	* The image's shorter side had been rescaled to 256 pixels and then cropped from middle to 256 by 256.
	* The mean activity was subtracted from each pixel.

* Activation
	* ReLU
		* Formula -- max(0,x)
		* Why preferred over sigmoid and tanh?
			 * Gives a faster learning rate which is good for large networks as it's gradient does not saturate even for high values

* Local Response Normalization
	* Local normalization scheme was used to aid generalization after ReLU.
	* This layer is somewhat like Batch Norm.
	* A good article on [LRN](https://prateekvjoshi.com/2016/04/05/what-is-local-response-normalization-in-convolutional-neural-networks/)

* Architecture
	* Overview --
		*  8 layers with weights
		* First 5 convolutional layers
		* 3 Fully Connected layers
		* 1000 way softmax
	* Key points:
		* Normalization after 1st and 2nd layers
		* Max polling after normalization and fifth convolutional layer
		* ReLU after every convolutional layer
		* First layer uses a 11x11x3 kernel with stride 4

* Data Augmentation [To reduce overfitting]
	* Image translated and horizontal reflection used (Not vertical since it would make no sense)
	* Altered the intensities of RGB channel (The intensities of all images should be same since on different days the intensities of image may be different [Like in rain or while cloud cover])
	* Dropout
		* A 0.5 probability dropout was applied
		* It reduces complex co-adaptation of neurons since a neuron can't rely on the presence of particular other neuron
	* Applied on fully connected layers

* Optimizer
	* A 128 length batch gradient descent was applied with 0.9 momentum
	* Learning Rate --
		* Divide the learning rate by 10 when validation error stops improving
		* Started with 0.01 ended in 0.00001

## Discussion
* Receptive field of first convolution layer is very large which may lead to over fitting due to large number of parameters alternatively, same receptive field can be realised by using deep network with small kernel size.
* Dropout means randomly removing the given fraction of neurons from the layer. It does not mean removing the neurons whose probability in the randomly generated matrix is greater or less that a given fraction (Wrong interpretation from Andrew NG exercise)


## Homework

-- Complete till 4th Course 2nd Week of deeplearning.ai
-- Read the AlexNet paper carefully
-- Enjoy Srijan

## Credits

*Conducted by:* [Udbhav Bamba](https://github.com/ubamba98) on 06-03-2019

*Report compiled by*: Ankesh Raj
