
# Session 9
 Paper reading session Very Deep Convolutional Networks For Large-Scale Image Recognition by K Simonyan et al.(2014)

## Resources
 Link to paper -- [Very Deep Convolutional Networks For Large-Scale Image Recognition](https://arxiv.org/pdf/1409.1556.pdf)
 
## Summary
* Introduction
   * Accuracy of model can be increased significantly by increasing depth (16-19) layers model and using small (3 x 3) convolution filters.
   * This model basically improves (Krizhevsky et al., 2012) model by using small filters,small strides and using better cropping and scaling.

* Architecture

    ![alt text](https://neurohive.io/wp-content/uploads/2018/11/Capture-564x570.jpg)

    * Input :
       *  Fixed size 224 x 224 RGB image.
    * Preprocessing-
       * Subtracting the mean RGB value.
    * Overview:
       * Five (2 x 2) Max pool layers with stride=2.
       * 3 FC layers (First two - 4096 channels).
       * Third FC layer - 1000 way softmax.
    * Key Points:
       *  (1 x 1) filters are used followed by non-linear function to give non-linearity to input channels.
       * Padding = 1 pixel for (3 x 3) conv layers.
       *  LRN did not worked well in improving accuracy so LRN was only used once in A-LRN (11 layers) model.
       *  ReLu activation function was used for all hidden layers.


* Discussion

     * Krizhevsky et al., 2012 (11 × 11 with stride 4),and 7 × 7 with stride 2 in (Zeiler & Fergus,2013; Sermanet et al., 2014) uses large receptive field.
     *   VGG uses small receptive field of (3 x 3) with stride 1.
     * Stack of two 3 x 3 and three 3 x3  without pooling is equal to effective receptive field of 5 x 5 and 7 x 7 respectively.
     * Above step makes decision function more discriminative (3 non-linear ReLu).
     * 3 (3 x 3) layers decreases parameters by approx 81 % w.r.t. (7 x 7) .
     * 1 x 1 is used to increase the non-linearity of the decision function without affecting the receptive fields of the conv. Layers.


* Training
    * Trained on multi scale training images (diff from AlexNet).
    * Overview:
       * Optimizer=multinomial logistic regression.
       * Mini Batch gradient descent (batch size=256).
       * Momentum=0.9.
       * L2 penalty multiplier=5 x 10^−4.
       * Dropout=0.5 (first two FC layer).
    * Learning rate=Initially set to 10^−2, and then decreased by a factor of 10 when the validation set accuracy stopped improving.
    * learning rate was decreased 3 times and learning was stopped after 370K iterations (74 epochs).
    * Takes less epochs to coverge due to-
      * Implicit regularisation imposed by greater depth and smaller conv.filter sizes.
      * Pre-initialisation of certain layers.

    * Initialization -
       * Deeper Model was initialized by using layers of model A(trained with random initialization ) without changing learning rate.
       * Remaining layers initialized randomly.
       * For random initialization weights were sampled from a normal distribution with the zero mean and 10^−2 variance.
       * Random cropping (224 x 224) and horizontal flipping,RGB color shift  for data augmentation.
    * Trained on two fixed scale s=256 and s=384 and multi scale chosen from range [256,512].


* Testing
    *  Re-scaled to smallest side Q (!=S).
    * Images were evaluated using dense and multi crop evaluation.
    * In dense evaluation, the fully connected layers are converted to convolutional layers at test time (the first FC layer to a 7 × 7 conv. layer, the last two FC layers to 1 × 1 conv. layers) and the uncropped image is passed through the fully convolutional net to get dense class scores. Scores are averaged for the uncropped image and its flip to obtain the final fixed-width class posteriors.
    * Test set was augmented by horizontal flipping of the images; the soft-max class posteriors of the original and flipped images are averaged to obtain the final scores for the image.
    * Key Points:
       * Using more than one values of Q for same S increased accuracy.
       * Multi-crop evaluation is complementary to dense evaluation due to different convolution boundary conditions:when applying a ConvNet to a crop, the convolved feature maps are padded with zeros, while in the case of dense evaluation the padding for the same crop naturally comes from the neighbouring parts of an image (due to both the convolutions and spatial pooling), which substantially increases the overall network receptive field, so more context is captured.

* Implementation Details
    * Each batch trained parallelly on multiple GPU’s and then taking average to get gradients of full batch.

* Single  Scale Evaluation
    * Model with (3 x 3) perform better than (1 x 1)  so it is important to capture spatial context.
    * Replacing two (3 x 3) by single (5 x 5)  increases error by 7%.
    * "Jittering" refers to the idea of adding small amounts of noise to your data to generate new, artificially corrupted examples. Theoretically, it is known to have a regularizing effect on the solution.
    * Scale Jittering is helpful for capturing multi-scale image statistics.
    * Q = S for fixed S, and Q = 0.5 x (S min + S max) for jittered S ∈ [S min , S max].


 * Multi Scale Evaluation
    * Evaluation:
       * Evaluated over three test image sizes close to training one.
       * For fixed S: Q = {S − 32, S, S + 32}.
       * For variable S: Q = {Smin, 0.5(Smin + Smax), Smax}.
       * Result = average of 3 rescaled version.
    * Key Points:
       * Scale jittering at training time allows the network to be applied to a wider range of scales at test time.
       * 16 and 19 layers model’s error decreased by 0.7% as compared to single scale.
       * Scale jittering, both at test time and training time, leads to better performance.

* Multi Crop Evaluation
    * Multi crop (error=24.6) is better than dense (error=24.8).
    * Multi crop and dense (error=24.4).

* ConvNet Fusion
    * Ensemble of 7 networks has 7.3% error.
    * Ensembling best two (16 layers model(3 x 3 conv layers) and 19 layers model)  error=7% dense and multi+dense error =6.8% (GoogleNet error=6.7%).

**In terms of the single-net performance, this architecture achieves the best result (7.0% test error).**

# Credits
*Conducted by:* [Udbhav Bamba](https://github.com/ubamba98) on 23-03-2019.

*Report compiled by:* [Sachin Shukla](https://github.com/ss407102)
