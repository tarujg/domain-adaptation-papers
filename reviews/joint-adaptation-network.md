# Deep Transfer Learning with Joint Adaptation Networks

Long, Mingsheng and Cao, Yue and Wang, Jianmin and Jordan, Michael I., ICML, 2017

## Summary

This paper introduces a framework for deep transfer learning using a joint adaptation network, where-in the joint distributions of multiple domain-specific layers are used across domains for unsupervised domain adaptation through a joint maximum mean discrepancy metric.

Its main contributions as opposed to the earlier works on deep adaptation:
- Reduces the shift in joint distributions of activations of various task-oriented layers by tying the layers via a common discrepancy metric across. 
- Uses an adversarial approach for optimal matching of the distributions in the source and target domain to get more differentiable features.

## Strengths

- Directly model and match joint distributions of the network activations of different task-specific layers, instead of computing a layer-wise discrepancy to model different layer-wise dependencies to approximate the shift in distributions.
- It efficiently computes the discrepancy that can be scaled linearly for large sample sizes and can be extended to most deep neural architectures. It is based on embedding the joint distributions in a tensor-product Hilbert space.
-  Using a domain adversarial deep network that maximizes JMMD ensures that source and target domains are made more distinguishable.

## Weaknesses
- Although the network proposes a method for joint adaptation using JMMD the computation of the metric varies drastically for ResNet and AlexNet and there seems to be no universal method of analysis for diverse network architectures for the same. 
- There is no method mentioning which layers are transferable for different backbone architectures.
- For certain tasks adaptation tasks different networks marginally outperform the JAN method.

## Critique of experiments
- Experiments carried out using AlexNet and ResNet and unsupervised domain adaptation is carried out for cross-domain & simulation-to-real datasets(Office-31 and ImageCLEF-DA).
- Approaches based on deeper network architectures like ResNet outperform AlexNet based networks showing that ResNet learns more abstract feature representations, therefore, reducing the alignment between domains. 
- Deep transfer learning approaches that reduce discrepancy with embedding modules learn transferable features compared to shallow transfer learning approaches as well as vanilla deep learning modules.
- Improvement of JAN to JAN-A shows that adapting domains against deep features where their distributions maximally differ ends up learning features indistinguishable across domains by maximization of the JMMD criterion as a domain adversary.
- Deep learning-based methods significantly outperform conventional shallow transfer learning.
- ImageCLEF-DA has more balanced domain sizes than Office-31 and there is a marginal improvement in accuracy for both backbone architectures showing that domain size may be contributing to the differences in alignment.

## Possible extensions

- The authors have assumed that the feature maps for source and target distributions are similar which has to be shown and not assumed. There needs to be an approach across feature maps.
- There needs to be an approach for approximating the universal kernel used for target and source domain distribution matching.

