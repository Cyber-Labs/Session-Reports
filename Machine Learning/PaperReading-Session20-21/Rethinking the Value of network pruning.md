
# Paper Reading Session 01
 Paper reading session RETHINKING THE VALUE OF NETWORK PRUNING by Zhuang Liu1, Mingjie Sun2, Tinghui Zhou1, Gao Huang2, Trevor Darrell Published as a conference paper at ICLR 2019.

## Resources
 Link to paper -- [Rethinking the Value of Network Pruning](https://arxiv.org/abs/1810.05270)
 
## Summary
   ![Training--->Pruning-->Fine Tuning](https://user-images.githubusercontent.com/8370623/67258108-e98f9c80-f443-11e9-9146-9a8333c6f318.png)

* Introduction
   * Used for reducing the heavy inference cost of deep models in low-resource settings.
   * In any Deep model more than 90% weights are of no use as compared to the other,we can get comparable accuracies even with 10% of the weights.
   * A typical pruning algorithm is a three-stage pipeline, i.e., training (a large model), pruning and fine-tuning
   * This paper shows that for **structured** pruning, **training the pruned model from scratch can almost always achieve comparable or higher level of accuracy than the model obtained from the typical "training, pruning and fine-tuning" procedure**
   * It can be concluded that for those pruning methods:
	1. Training a large, over-parameterized model is often not necessary to obtain an efficient final model.
	2. Learned “important” weights of the large model are typically not useful for the small pruned model. 
	3. The pruned architecture itself, rather than a set of inherited “important” weights, is more crucial to the efficiency in the final model, which suggests that in some cases pruning can be useful as an architecture search paradigm.
   * Addresses the problems faced by others while trying to violate Lottery Ticket Hypothesis.Train pruned networks more to get comparable accuracies.
   

* Implementations

    * Key Points:
       *They evaluated the following seven pruning methods. 
       1. [L1-norm based channel pruning](https://arxiv.org/abs/1608.08710)
       2. [ThiNet](https://arxiv.org/abs/1707.06342)
       3. [Regression based feature reconstruction](https://arxiv.org/abs/1707.06168)
       4. [Network Slimming](https://arxiv.org/abs/1708.06519)
       5. [Sparse Structure Selection](https://arxiv.org/abs/1707.01213)
       6. [Soft filter pruning](https://www.ijcai.org/proceedings/2018/0309.pdf)
       7. [Unstructured weight-level pruning](https://arxiv.org/abs/1506.02626)


* Methodology

     * Used Scratch-E to denote training the small pruned models for the same epochs, and Scratch-B to denote training for the same amount of computation budget
     * Trained pruned models for more epochs.
     * One may argue that we should instead train the small target model for fewer epochs
since it may converge faster. However, in practice we found that increasing the training epochs
within a reasonable range is rarely harmful.


* Lottery Ticket Hypothesis
    * The Lottery Ticket Hypothesis: A randomly-initialized, dense neural network contains a subnetwork that is initialised such that — when trained in isolation — it can match the test accuracy of the original network after training for at most the same number of iterations. — Frankle & Carbin (2019, p.2)
    * This paper breaks this Hypothesis,showed significant results even after violating this hypothesis.

    
**This paper led the foundation of lot more pruned architectures.**

# Credits
*Conducted by:* [Udbhav Bamba](https://github.com/ubamba98) on 05-08-2020.
*Explained by:* [Rishabh Tiwari](https://github.com/rishabh-16)
*Report compiled by:* [Harsh Mishra](https://github.com/MiHarsh)
