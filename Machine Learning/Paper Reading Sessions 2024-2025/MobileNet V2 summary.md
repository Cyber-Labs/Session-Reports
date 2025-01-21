The two papers introduce different versions of MobileNets, which are efficient convolutional neural networks designed for mobile and embedded vision applications. Both papers focus on reducing computational cost and model size while maintaining reasonable accuracy.

**MobileNet v2**

*   **Core Idea**: MobileNet v2 introduces the **inverted residual with linear bottleneck**. This module expands a low-dimensional compressed representation to a higher dimension, filters with depthwise convolution, and then projects back to a low-dimensional representation with a linear convolution.
*   **Inverted Residual Structure:** The shortcut connections are between the thin bottleneck layers, unlike in traditional residual networks. The intermediate expansion layer uses lightweight depthwise convolutions for filtering.
*   **Linear Bottlenecks:** The paper finds that removing non-linearities in the narrow layers is important to maintain representational power. Linear layers are crucial because they prevent non-linearities from destroying too much information.
*   **Depthwise Separable Convolutions:** Similar to MobileNet v1, MobileNet v2 uses depthwise separable convolutions to reduce computational cost.
*   **Hyperparameters:** MobileNet v2 also uses the input image resolution and width multiplier as tunable hyperparameters. The width multiplier is applied to all layers except the last convolutional layer.
*   **Network Structure:** The MobileNet v2 architecture consists of an initial fully convolutional layer followed by 19 residual bottleneck layers. It uses ReLU6 as the non-linearity.
*   **Memory Efficiency**: The inverted residual bottleneck layers allow memory-efficient implementation. By treating a bottleneck residual block as a single operation, the total memory is dominated by the size of bottleneck tensors, rather than the size of larger internal tensors.
*   **Applications:** MobileNet v2 achieves state-of-the-art performance on multiple tasks, including ImageNet classification, COCO object detection with SSDLite, and semantic segmentation with Mobile DeepLabv3.

**Differences between MobileNet v1 and v2**

*   **Core Building Block:** MobileNet v1 uses depthwise separable convolutions as its main building block, while MobileNet v2 introduces the inverted residual structure with linear bottlenecks.
*   **Residual Connections:** MobileNet v1 does not explicitly use residual connections, while v2 uses inverted residual connections, where shortcuts are between bottleneck layers.
*   **Non-linearities:** MobileNet v1 uses ReLU non-linearities throughout the network, while MobileNet v2 removes non-linearities in the narrow bottleneck layers, using linear layers in those parts.
*   **Memory Efficiency:** MobileNet v2 introduces a more memory efficient design by minimizing the need to materialize large intermediate tensors during inference. This is achieved by utilizing bottleneck tensors.
*   **Performance:** MobileNet v2 improves upon MobileNet v1 in terms of accuracy, computational cost and model size across several benchmarks. It also provides an improvement on object detection when using the new SSDLite framework.

**Key Takeaways**

*   **Depthwise Separable Convolutions:** Both papers highlight the importance of depthwise separable convolutions in creating efficient neural networks for mobile devices. They allow for significant reduction in computational cost and model size with minimal impact on accuracy.
*   **Importance of Bottlenecks:** MobileNet v2 introduces the use of linear bottlenecks to preserve information and improve performance. This design choice is a crucial improvement over MobileNet v1.
*   **Hyperparameter Tuning:** Both architectures make use of hyperparameters like width and resolution multipliers to further customize models based on the application requirements.
*   **Practicality:** Both papers emphasize the practical application of the introduced models in real-world scenarios, demonstrating their effectiveness in different tasks. MobileNet v2 is particularly tailored to mobile and resource constrained environments.
*   **Memory efficiency:** MobileNet v2 provides a much more memory efficient model, that allows for use in embedded systems with small caches.
* **Separation of Expressiveness and Capacity**: MobileNet v2 allows for the separation of the expressiveness and capacity of the network, which can be used to study network properties.

In summary, MobileNet v1 laid the groundwork for efficient mobile neural networks using depthwise separable convolutions. MobileNet v2 built upon this foundation by introducing inverted residuals with linear bottlenecks, resulting in a more efficient and accurate architecture. Both papers provide valuable insights into designing neural networks for resource-constrained environments.
