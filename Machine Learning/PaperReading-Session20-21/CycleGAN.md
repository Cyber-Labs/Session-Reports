# Paper Reading Session 04
**Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks** by *Zhu, Jun Yan Park, Taesung Isola, Phillip Efros, Alexei A.*.

## Resources
Paper link: https://arxiv.org/abs/1703.10593

### Introduction
- Introduces an approach for learning to translate an image from a source domain X to a target domain Y in the absence of paired examples.
-	Goal is to learn a mapping G : X → Y such that the distribution of images from G(X) is indistinguishable from the distribution Y using an adversarial loss. Because this mapping is highly under-constrained, couples it with an inverse mapping F : Y → X and introduces a cycle consistency loss to enforce F(G(X)) ≈ X (and vice versa).
-	

### Formulation

