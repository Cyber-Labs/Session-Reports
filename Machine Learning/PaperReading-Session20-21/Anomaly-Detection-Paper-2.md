## Sub-Image Anomaly Detection with Deep Pyramid Correspondences

#### Some Problems addressed in this paper
> ##### Unexpectedness of Anomalies  
> Usually in most of the CV task the distribution in train and test are same but this is not the case with anomaly detection. This paper uses normal images( that is the one with no anomalies ) and uses semi supervised learning. 

> ##### Localization of Anomalies
> This paper not only detects anomalies but also locates them, which makes the algorithm more explainable.

#### Previous Works

##### Image-level
> Reconstruction-based methods learn a set of basis functions on the training data, and attempt to reconstruct the test image using a sparse set of these basis function. If the test image cannot be faithfully reconstructed using the basis functions, it is denoted as anomalous, as it is likely that it came from a different basis from that of the normal training data

> Distribution-based method: The main principle is to model the probability density function (PDF) of the distribution of the normal data. Test samples are evaluated using the PDF, and test samples with low probability density values are designated as anomalous.

> Classification-based method: Simply making a classification model to detect whether a particular image contains anomalies or not. Self-supervised learning was also proposed in some paper.

#### Method

Consists of three main parts

- ###### image feature extraction:
ResNet feature extractor pre-trained on the ImageNet dataset was used instead of an extractor based on some small dataset( particular to this task ). Feature vector obtained after global pooling the last convolutional layer was taken

- ###### K Nearest Neighbor Normal Image Retrieval
For a given test image y, K nearest normal images from the training set was retrieved, N k (f y ). The distance is measured using the Euclidean metric between the image-level feature representations

Images are labelled at this stage as normal or anomalous. Positive classifica tion is determined by verifying if the kNN distance is larger than a threshold τ .

- ###### Sub-image Anomaly Detection via Image Alignment And Feature Pyramid Matching
For feature extraction, last M layers of Resnet was taken so as to capture both global context(from earlier ones) and fine-grained local features (from later ones). Deep features at every pixel location p ∈ P using feature extractor F (x i , p) of the relevant test and normal training images were extracted and a gallery of features at all pixel locations of the K nearest neighbour is constructed. The anomaly score at pixel p, is given by the average distance between the features F (y, p) and its κ nearest features from the gallery. For a given threshold θ, a pixel is determined as anomalous if d(y, p) > θ, that is, if we cannot find a closely corresponding pixel in the K nearest neighbor normal images.

```
d(y, p) =  summation(||f − F (y, p)||^2)
```

