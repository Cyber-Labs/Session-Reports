# Paper Reading Session 4

**Uninformed Students: Student–Teacher Anomaly Detectionwith Discriminative Latent Embeddings**

**Paper link**: https://arxiv.org/abs/1911.02357

## Introduction
This paper talks about anomaly detection using a student teacher method of training. Anomalies are detected when the outputs of the student networks differ from that of the teacher network. The intrinsic uncertainty in the student networks is used as an additional scoring function that indicates anomalies.

*Task: Anomaly detection using unsupervised learning*\

## Key points
- Training adversarial networks (GAN) was an alternative way used to detect anomaly but it had shortcomings.
- Once the student model has learned sufficiently from the teacher model, which inturn was trained on a large dataset of patches from natural images, we can get a dense anomaly score for each input pixel which takes into account students' predictive uncertainty and the regression error w.r.t teacher. It is shown that students will generalize poorly outside the manifold of anomaly-free training data  and start to make wrong predictions.
- Results from this approach of training are compared with other state of art techniques further in this paper.
- Promising results have been achieved by transferring discriminative embedding vectors of pretrained networks to the task of anomaly detection by fitting shallow machine learning models to the features of anomaly-free training data.

## Student–Teacher Anomaly Detection
- Given an anomaly free dataset, the teacher network is trained and an ensemble of student networks is created which learns from the teacher network that can later detect anomalies in test images. 
- The student model is capable of assigning scores to every pixel indicating how much it deviates from training data.For this, the student models are trained against regression targets obtained from a descriptive teacher network T pretrainedon a large dataset of natural images.

## Learning local patch descriptors (Teacher Network)
- This section describes training of teacher network T, using metric learning and knowledge distillation techniques. Teacher network T will efficiently output descriptors for every possible square of side length ‘p’ within the input image. T is obtained by first training a network T^ to embed patch-sized images into a metric space of dimension d using only convolution and max-pooling layers. Fast dense local feature extraction for an entire input image can then be achieved by a deterministic network transformation of T^ to T. A large number of training patches p can be obtained by random crops from any image database. ImageNet is used here.

**Knowledge distillation**: Sort of transfer learning. We distill the knowledge of a powerful pretrained network P into T^ by matching the output of P with a decoded version of the descriptor obtained from T^.

**Metric Learning**: If for some reason pretrained networks are unavailable, one can also learn local image descriptors in a fully self-supervised way. Details are mentioned in the paper.

## Ensemble of Student Networks for Deep Anomaly Detection
- Student networks are trained such that for an input image I, each student outputs its predictive distribution over the space of possible regression targets for each local image region p centered at row r and column c. Note that the students’ architecture with a limited receptive field of size p allows us to obtain dense predictions for each image pixel with only a single forward pass, without having to actually crop the patches p. Loss and metic are mentioned in paper.

## Scoring Functions for Anomaly Detection
- Having trained each student to convergence, a mixture of Gaussians can be obtained at each image pixel by equally weighting the ensemble’s predictive distributions. The scoring function  takes into account students' predictive uncertainty and the regression error w.r.t teacher of a particular pixel. Combining both we can predict for each pixel being anomalous or not.

*Experiments are performed by selecting different patch size p which was introduced earlier.*
**Dataset used were MNIST and CIFAR-10 and MVTec Anomaly Detection Dataset.**

## Conclusion
This paper  proposed a novel framework for the challenging problem of unsupervised anomaly segmentation in natural images. Anomaly scores are derived from the predictive variance and regression error of an ensemble of student networks, trained against embedding vectors from a descriptive teacher network. Ensemble training can be performed end-to-end and purely on anomaly-free training data without requiring prior data annotation.  This approach can be easily extended to detect anomalies at multiple scales. Improvements over current state-of- the-art methods on a number of real-world computer vision datasets for one-class classification and anomaly segmentation was demonstrated.
