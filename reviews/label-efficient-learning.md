# Label Efficient Learning of Transferable Representations across Domains and Tasks

Zelun Luo, Yuliang Zou, Judy Hoffman, Li Fei-Fei, NeurIPS ‘2017

## Summary

This work solves the task of learning transferable knowledge from sparsely labeled target domains with possibly new tasks along with labeled sources with task annotations. It combines the idea of few shot learning, adaptation across domains and transfer learning across tasks. The approach is semi-supervised and does unsupervised feature alignment between source and target data and does semantic transfer from labeled(source or target) data to unlabeled target data and within target domain itself.

## Strengths

- Useful in practical scenarios as large-scale labeled domain isn’t available for lot of use cases and learns reusable and general purpose representations.
- The multilayer unsupervised domain adversarial approach gives better alignment between source and target with better classification results and more stable training.
- Has a novel cross-domain and intra-domain class similarity objective that can be used for for the scenario when source and targets have non-overlapping classes.
- Unlike previous entropy minimization approaches, they don’t assume that a target image maps to a single source label.

## Weakness
- For domain adversarial losses, the paper does not provide any basis for selection which layer activations to take as input for the discriminator.
- Due to the presence of the wide number of hyper-parameter such as alpha, beta in the loss objective and tau for temperature, and decay parameter gamma, fine-tuning will be difficult and has not been addressed in the paper.
- For the experiments in SVHN to MNIST task the results obtained are highly sensitive to the subsampled data.
- Although the pairwise similarity metric is proposed and has shown good results, it is highly computationally expensive.

## Critique of experiments
- SVHN 0-4 digits are the labeled source data and few labeled target MNIST (5-9) digits, along with remaining MNIST data as unlabeled target. The method outperforms fine-tuning approach significantly. 
- The temperature parameter is varied to show the normalizing nature of the parameter and also shows that source images similar to target image increases on increasing the parameter.
- Further experiments on the ImageNet object recognition task utilize the ResNet 18 embeddings with the few labeled UCF101 activity recognition clips. There is classification on each frame and also by taking the average of the softmax scores to show two different accuracy metrics.
- Ablation studies and comparative analysis with the state-of-art approaches such as ADDA, Gradient Reversal and Domain confusion show that the multilayer optimization approach leads to 6.5% improvement and increases optimization stability.

## Possible extensions
- The methodology has the scope to be extended to the scenario when there are multiple domains present, where-in we can have a slightly more complex similarity metric with multiple CNN heads corresponding to each domain.
