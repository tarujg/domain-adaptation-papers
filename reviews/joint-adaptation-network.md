# Deep Transfer Learning with Joint Adaptation Networks

Long, Mingsheng and Cao, Yue and Wang, Jianmin and Jordan, Michael I., ICML, 2017

## Summary

This paper introduces a framework for deep transfer learning using a joint adaptation network (JAN) using joint distributions of multiple domain-specific layers as a discrepancy metric for unsupervised domain adaptation.

Main contributions:
- Reduces the shift in joint distributions of activations of various task-oriented layers by tying the layers via Joint-MMD. 
- Applies an adversarial approach for optimal matching of target and source distributions to get more differentiable features.

## Strengths

- Directly models and matches joint distributions of the network activations of different task-specific layers based on embedding the joint distributions in a tensor-product Hilbert space, instead of computing a layer-wise discrepancy for alignment.
- Efficiently computes the discrepancy that linearly scales for sample sizes. 
-  Using a domain adversarial deep network that maximizes JMMD ensures that source and target domains are made more distinguishable.

## Weaknesses
- The computation of the JMMD metric varies drastically for ResNet and AlexNet and there seems to be no universal method of analysis for diverse network architectures for the same. 
- There is no protocol mentioning which layers are transferable for different backbone architectures.
- For certain adaptation tasks, residual transfer networks marginally outperform the JAN method.

## Critique of experiments
- Experiments carried out using AlexNet and ResNet for the unsupervised domain adaptation task for cross-domain & simulation-to-real datasets (Office-31 and ImageCLEF-DA).
- Approaches based on deeper network architectures like ResNet outperform AlexNet based networks showing that ResNet learns more abstract feature representations, therefore, reducing the alignment between domains. 
- Deep transfer learning approaches that reduce discrepancy with embedding modules learn transferable features compared to shallow transfer learning and vanilla deep learning modules.
- Improvement of JAN to JAN-A shows that adapting domains against deep features where their distributions maximally differ ends up learning features indistinguishable across domains by maximization of the JMMD criterion as a domain adversary.
- ImageCLEF-DA has more balanced domain sizes than Office-31 and there is a marginal improvement in accuracy for both backbone architectures showing that domain size may be contributing to the differences in alignment.

## Possible extensions

- It is assumed that the feature maps for source and target distributions are similar, which might not necessarily be the case. There needs to be an approach to align feature maps.
- An approach to approximate the universal kernel needs to be formulated for matching the target and source domains.
