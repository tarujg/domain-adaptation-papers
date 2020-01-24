# Learning Transferable Features with Deep Adaptation Networks

Long, Mingsheng and Cao, Yue and Wang, Jianmin and Jordan, Michael I., ICML, 2015

## Summary

This paper introduces a deep neural network architecture for domain adaptation, in which all the layers corresponding to task-specific features are adapted in a layer-wise manner. Multiple kernels are used for adapting deep representations, which substantially enhances adaptation effectiveness compared to single kernel methods. 

The paper solves the following issues
- Feature transferability decreases with increasing task discrepancy.
- Higher layers are tailored to specific tasks in the deep networks and are therefore not always safely transferable. 
- Adaptation effect may vanish in back-propagation of deep networks

## Strengths

- It can learn unbiased deep transferable features with statistical guarantees.
- It proposes an optimal multi-kernel selection procedure for the reduction of the domain discrepancy.
-  Adapting a single layer might not reverse the dataset bias since there are multiple layers that learn source-specific features. This may not necessarily be the case and the earlier layers of the network may have learned some non-general features too.

## Weaknesses
- AlexNet is one of the earliest architectures which they have explored in the current paper. They could have tried a comparative result of deeper networks such as VGGNet as well to show relative adaptation of layers in these. No comparison of the MMD-based approach with standard and more powerful networks like ResNet.
- In the experiments of the paper, there seems to be an underlying assumption that the final layers have specifically learned source-related features. But this may not necessarily be the case and the earlier layers of the network may have learnt some non-general features too.
## Critique of experiments
- Experiments carried out on AlexNet pre-trained on ImageNet fine-tuned on Office and Caltech datasets with 12 adaptation tasks for unsupervised adaptation and semi-supervised adaptation.
- Deep learning-based methods significantly outperform conventional shallow transfer learning.
- By comparing DAN with single-layer approaches DDC, DAN7, DAN8 it is seen that Deep adaptation of multiple layers outperforms shallow adaptation of one hard-to-tweak layer.
- Two samples can be matched better by Multiple Kernel-MMD as compared to Single Kernel-MMD.
## Possible extensions

- One of the shortcomings was the lack of powerful representations and networks used for analysis such as DenseNet, ResNet and Inception and other deeper architectures which would give more concrete proof for the main idea of the paper.
- There is not much work done for applying the adaptation techniques on the Conv layers, which could be explored to show how deep features can be transferred.
