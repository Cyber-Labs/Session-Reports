## Modeling the Distribution of Normal Data in Pre-Trained Deep Features for Anomaly Detection <br>

[Link to the paper](https://arxiv.org/pdf/2005.14140.pdf)

### Aim:

To demonstrate the effectiveness of pre-trained deep feature representations transferred to the Anamoly Detetection task by fitting a multivariate Gaussian to normal data of deep features learned by ImageNet training and using the Mahalanobis distance

### Benefit of this approach:

1. Outperformed the benchmark set by prior state of the art on MVTec dataset.
2. Gained insight into and explained the discriminative nature of pre-trained deep features by means
   of Principal Component Analysis (PCA).

### Key points:

1. Anomalies are rare events, i.e. their prevalence in the
   application domain is low.
2. Anomaly appearance is not well-defined (i.e. anomalies
   types are ambiguous).
3. As a result, AD datasets that are heavily imbalanced, often containing only few anomalies for
   model verification and testing.
4. Principal components that retain little variance in normal
   data are highly discriminative to the AD task, indicating that
   learning these features from scratch may be difficult using
   normal data only.

### Method

1. Used EfficientNet and ResNet for feature extraction.
2. Average pooling is employed.
3. They compared their approach to two different assumptions:

   (I) When assuming a fixed-variance univariate Gaussian distribution, the anomaly score reduces to the simple L2-distance
   to the mean of the training set.

   (II) When assuming a feature independent univariate Gaussian, an anomaly score can be
   defined with the standardized Euclidean distance

### Learning:

1.  Deeper feature representations are more suitable
    for AD in a transfer learning settin
2.  The multivariate Gaussian is best suited for AD due to its high and robust performance.
3.  Deeper feature representations are more suitable
    for AD in a transfer learning settin
4.  Using PCA, it is found that principal components
    containing only little variance in normal data are ultimately
    those necessary for discriminating between normal and anomalous images.

### Recommended

Read the appendix of the paper to get a clear idea of the second point under Method.
