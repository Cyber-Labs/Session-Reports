<!-- 
 - Replace all the {} with their values. Name this file as Session {Session no.}.md (without braces) and submit a PR.
-->
# Paper-Reading Session: DenseNet
Conducted on: 05/12/2023

## Agenda
Discussion over Densely Connected Convolutional Networks (DenseNet) .

## Resources
Paper link: https://arxiv.org/abs/1608.06993

## Session Summary
### Paper Discussion
Discussed by Neerukonda Sharvan Chowdary, assited by Dheemant Dixit and Shreshth Sharma.

### Doubt Discussion
Narrow filter size of layers, Concatenation over Element-wise addition, Importance of short connections.

### Discussion on UBC
Discussion over potential methods of working with images of extremely large sizes. 

#### Feasible approach
Using conv layers to shrink image size and then using *ResNet18* or *ResNet34* to generate image embeddings.

### Kaggle tips
#### Submitting kaggle notebooks without wasting GPU runtime. 
#### Detaching variables (such as *loss*) from the GPU to save GPU RAM.

## Agenda for the next session
Kaggle discussion over the competition: *UBC Ovarian Cancer Subtype Classification and Outlier Detection (UBC-OCEAN)*, tentatively on 07/12/2023.

## Credits
*Conducted by:* Neerukonda Sharvan Chowdary, Dheemant Dixit, Shreshth Sharma

*Report compiled by*: Alok Raj

*Absentees*: Karaka Prasanth Naidu
