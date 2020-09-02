# Paper Reading Session 2

## Fixing the train-test resolution Discrepancy

[Link to Paper](https://arxiv.org/pdf/1906.06423.pdf)

### Aim of the paper:
> Pointed out that present way of separate augmentation and optimization to both train and test has led to sigmnificant distribution shift between the train and test data.
> Shows that increasing the size of the crops used at test time compensates for randomly sampling the ROCs at training time. In other words, Lower resolution while training than at the test time gave better results.

### Benefit of this Approach:
> Due to lower resolution while training time significantly reduces the training time and also memory consumption which is essential while training on GPUs.
> Better or same accuracy as compared to precvious method

### Key Points:

- Considering RandomResizedCrop at train time and CenterCrop at test time it is shown that at testing time a object may appear as small as a third of what it appears at training time.
- Increasing or Decreasing the crop size affects the activation statistics measured after average pooling. Less crop size results in more sparse distribution and vice versa.
- Though increasing the test crop size affects the distribution or activation statistics but it is beneficial for the accuracy because it reduces the train-test size mismatch.

### Method

- Increasing the test images and also the test crop size to reduce the difference in apparent size of an object during test and train time.
- Adjusting the statistics before spatial pooling to "correct" the skewed activation statistics.


### Recommended
Read the appendix of the paper to get a clear idea of the second point under `Method`



