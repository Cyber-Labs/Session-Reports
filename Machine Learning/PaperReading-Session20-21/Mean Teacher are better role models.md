# Paper Reading Session 03
**Mean teachers are better role models: Weight-averaged consistency targets improve semi-supervised deep learning results** by *Antti Tarvainen, Harri Valpola*.

## Resources
Paper link: https://arxiv.org/abs/1703.01780
## Summary

### Introduction
-	This paper talks about how using mean teacher as role model in temporal ensemble and pi models can improve the test accuracy of the model.
-	It revolves around teacher-student training technique. As a student, it learns and as a teacher, it generates target labels which are later used by itself as student learning.
-	Two losses are used here. One is consistency loss and the other one is classification loss. Since the model itself generates the labels, there are very high chances that they would be incorrect. If this happens quite a lot, then consistency loss would go up.
-	The consistency cost is defined as the distance between student model’s predictions and that of the teacher model’s. Mean Squared Error has been used as consistency loss in this paper.
-	If too much weight is given to the generated labels, then the cost of inconsistency would outweigh the misclassification cost, thus, preventing the model from learning new things.
-	This problem can be solved by improving target quality. One way to do this is to choose the targets carefully, removing unwanted noises. Other way is to choose the teacher model carefully.
-	Noisy Teacher provides more accurate targets: SoftMax output does not provide accurate result outside training data and so we need to add noise at the inference time. This approach was used in Pseudo-ensemble agreement and this method is known as “Pi model”.
-	Temporal Ensemble: It maintains exponential moving average (EMA) of predictions for each training examples. EMA predictions of each minibatches are updated based on new predictions on each training step. Thus, this becomes the ensemble of predictions done by each version of model during the training phase. Since the update is done once per epoch, new information is added very slowly and so, temporal ensemble becomes slower as the size of dataset increases.


### Mean Teacher
-	Unlike temporal ensemble, it maintains EMA of model weights instead of predictions.
-	Teacher model is average of student models. It uses the EMA weights of student model instead of sharing weights with it.
-	Now it can aggregate new information at each step during an epoch. And, this improves the output of all layer, not just the top layer. These lead to two main advantages, first, more accurate target labels lead to faster feedback loops between the student and teacher models, giving better test accuracy. Second, this approach, being much faster, can be used in case of larger datasets and on-line learning, which was problematic to do in case of temporal ensemble.

### Experiments
-	Using Mean Teacher on top of Pi model and temporal ensemble increased test accuracy on semi-supervised tasks on Street View House Number (SVHN) dataset.
-	Mean Teacher is good when labelled data is less. When using 500 labels, Mean Teacher learns faster and keeps on improving even after the Pi model stops learning. In case of all-labelled data, Mean Teacher and the Pi model behave almost identically. Mean Teacher learns faster and converges to better results but also, increasing the number of training examples (labelled/ unlabelled) allows the Pi model to improve longer and can increase model’s accuracy.
-	In this paper, the authors used EMA decay α=0.99 in the evaluation runs during the ramp-up(early) phase and α=0.999 during rest of the training phase. This was done because the student learns very quickly during the early phase and so, the teacher should forget older, inaccurate student weights (α=0.99). Later, the student improves slowly and has become quite accurate in predictions, so teacher should remember these new student weights (α=0.999). Note that assigning α=0 will make Mean Teacher an ineffective version of Pi model because the teacher will only use student model’s latest weights and not the EMA weights, plus, the gradient flow will occur only through the student’s side.
-	Altering the coupling strength of classification and teacher-student consistency may change the performance of the model. Strongly coupled model performs better in comparison with  loosely coupled model.
-	Best choice for consistency cost function would be MSE even though KL-Divergence would seem more of a natural choice. The exact reason behind this still remains unclear. This might be related to the confidence of teacher predictions but no experiment was performed to back this up.

### Conclusion
In this paper, the authors proposed Mean Teacher, a method that averages model weights to form a target-generating teacher model. Unlike Temporal Ensemble, Mean Teacher works with large datasets and on-line learning. Experiments suggest that it improves the speed of learning and the classification accuracy of the trained network. In addition, it scales well to the state-of-art architectures and larger image sizes.

## Credits
- Meeting by: [Udbhav Bamba](https://github.com/ubamba98)
- Paper explained by: [Saksham Aggarwal](https://github.com/saksham20aggarwal)
- Report by: [Piyush Pandey](https://github.com/P-yushh)
- Dated 19/08/20
