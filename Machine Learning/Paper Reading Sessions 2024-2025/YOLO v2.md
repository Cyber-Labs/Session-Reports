# Core Ideas of YOLO v2

## 1. Improved Bounding Box Predictions
- **Anchor Boxes**: Introduced to predict offsets relative to predefined shapes, enabling detection of objects with varying sizes and shapes.
- **Multiple Boxes per Grid Cell**: Overcomes YOLO v1's limitation of detecting only one object per cell.

## 2. High-Resolution Classifier Pretraining
- Pretrained on high-resolution (448x448) ImageNet images, improving accuracy for small and overlapping objects.

## 3. Batch Normalization
- Applied after every convolutional layer to stabilize training, improve convergence, and reduce dependency on dropout.

## 4. Multi-Scale Training
- Input image size is randomly resized during training, enhancing generalization to varying image resolutions.

## 5. Feature Pyramid with Darknet-19
- Introduces **Darknet-19**, a 19-layer CNN optimized for speed and accuracy with 5 max-pooling layers.

## 6. Direct Location Prediction
- Uses a sigmoid function to constrain box center coordinates within grid cells, improving prediction stability.

## 7. Fine-Grained Features via Pass-Through Layer
- Pass-through layers concatenate low-level and high-level features, aiding in detecting smaller objects.

## 8. Hierarchical Classification
- Utilizes class hierarchies (e.g., animal → dog → breed) to improve classification accuracy on large-scale datasets.

---

# Network Architecture
### Darknet-19 Backbone
- **Structure**: 19 convolutional layers with batch normalization and leaky ReLU activations.
- **Output**: Predicts bounding box coordinates, objectness scores, and class probabilities for each anchor box in grid cells.

---

# Key Achievements
1. **Accuracy**: Higher mAP than YOLO v1, surpassing SSD in speed and accuracy.
2. **Speed**: Maintains real-time performance at **67 FPS** on 416x416 input resolution.
3. **Scalability**: Multi-scale training and anchor boxes improve robustness for varying object sizes and complex scenes.

---

# Challenges
- Still struggles with detecting very small objects compared to advanced detectors like Faster R-CNN.
