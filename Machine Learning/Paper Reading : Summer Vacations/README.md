
# Paper Reading : Summer Vacations
Paper Reading - Going Deeper With Convolutions by Szegedy et. al. (2014) 

# Resources
Link to Paper - [Going Deeper With Convolutions](https://arxiv.org/abs/1409.4842)

# Summary

 * Abstract
 
	 * winning model of ILSVRC 2014
	 *  *Hallmark of model* : increasing depth and width of the model while keeping the computational budget constant
	 * based on Hebbian Principal ( neurons that fire together, wire together) i.e. clustering neurons with highly correlated outputs.
	 
* Introduction

	* uses 12 times less parameters than VGG-16
	* computational budget = 1.5 billion (could be used for real world use at a resonable cost)
	
* Problems Addressed

	* Overfitting : major bottleneck, needs huge datasets (can't even be produced by augmentation)
	* Computation : with increase in size computation increase drastically and if computation power is used inefficiently (eg- Weights ~ 0) then a lot of computation is wasted.
	* **Common Solution -** Replacing FC layers with sparsely connected Convolutional Layers, thus decreasing the number of parameters along with overfitting and computation.
	
# Architectural Details

## Inception Module

#### Naive Form
![
](https://cdn-images-1.medium.com/max/800/1*DKjGRDd_lJeUfVlY50ojOA.png)

* *Problem* : convolutions with high receptive fields merging of pooling layers with convolutional layers leads to a computational blow up within a few stages


### Inception module with dimension reductions
![
](https://cdn-images-1.medium.com/max/800/1*U_McJnp7Fnif-lw9iIC5Bw.png)

* 1 X 1 convolutions are used to compute reductions before the expensive 3 X 3 and 5 X 5 convolutions
* 1 X 1 also adds non linearity in the model due to use of relu activation fuction, thus making them dual purpose

* *Benefits* : 
	* increasing number of units without computational blow-up.
	* compatible with the intuition that visual information should be processed at various scales

## GoogLeNet

![
](https://cdn-images-1.medium.com/max/800/1*uW81y16b-ptBDV8SIT1beQ.png) 

* Yellow boxes are **auxillary classifiers**, during training their loss gets added to the total loss ( weighted 0.3 ).
	* increases the gradient signal propagated back
	* additional regularization
	* Structure
		*    average pooling layer with  **5 × 5**  filter size and  **stride 3**, resulting in an  **4 × 4 × 512** output for the  _(4a)_, and  **4 × 4 × 528**  for the  _(4d)_  stage.
		* **1 × 1**  convolution with  **128 filters** and rectified linear activation.
		*    FC layer with  **1024 units**  and rectified linear activation.
		*    Dropout 0.7
		*    linear layer with softmax loss as the classifier _(removed at inference time)_

# Training

* asynchronous SGD with 0.9 momentum
* fixed learning rate schedule (decreasing the learning rate by 4% every 8 epochs)
* Polyak averaging used at inference time.
* sampling of various sized patches of the image whose size is distributed evenly between 8% and 100% of the image area, aspect ratio between 3/4 and 4/3
* random interpolation methods (bilinear, area, nearest neighbor and cubic, with equal probability)

# Testing
* trained 7 versions of GoogLeNet model with same initialisation ( differ in sample methodologies )
* resizing image to 4 scales (256, 288, 320 and 352) and then taking left, center and right square, then taking 4 corners and the center **224 X 224** crops along with mirrored versions. Total crops = **144**
*  Softmax probabilities are averaged over multiple crops to obtain the final prediction

# Results

* _Top-5 Error_ : **6.67%** on both validation and testing data ranking 1st.
	* VGG Error : 7.32% on testing data ranking 2nd. 

# Credits
_Summary compiled by: [Rishabh Tiwari](https://github.com/rishabh-16)_
