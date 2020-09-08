# Paper Reading Session 04
**Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks** by *Zhu, Jun Yan Park, Taesung Isola, Phillip Efros, Alexei A.*.

## Resources
Paper link: https://arxiv.org/abs/1703.10593

### Introduction
- Introduces an approach for learning to translate an image from a source domain X to a target domain Y in the absence of paired examples.
-	Goal is to learn a mapping G : X → Y such that the distribution of images from G(X) is indistinguishable from the distribution Y using an adversarial loss. Because this mapping is highly under-constrained, couples it with an inverse mapping F : Y → X and introduces a cycle consistency loss to enforce F(G(X)) ≈ X (and vice versa).
-	

### Formulation






- Our goal is to learn mapping functions between two domains X and Y given training samples {xi}N i=1 where xi ∈ X and {yj}M j=1 where yj ∈ Y1. We denote the data
distribution as x ∼ pdata(x) and y ∼ pdata(y).our model includes two mappings G : X → Y and F : Y → X. In addition, we in- troduce two adversarial discriminators DX and DY, where DX aims to distinguish between images {x} and translated images {F(y)}; in the same way, DY aims to discriminate between {y} and {G(x)}



### Implementation
-	Network Architecture: Uses 6 residual blocks for 128 × 128 training images, and 9 residual blocks for 256 × 256 or higher-resolution training images





## Credits
- Meeting by: [Udbhav Bamba](https://github.com/ubamba98)
- Paper explained by: [Prateek Bedre](https://github.com/pratikb2805)
- Report by: [Taresh Rajput](https://github.com/taresh18)
- Dated 31/08/20
