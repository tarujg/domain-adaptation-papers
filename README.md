# Domain Adaptation in Computer Vision


In recent years, while we are trying to attain the longterm computer vision task of creating smart machines that learn by visual exploration of world. We are currently trying to build on the immediate goal of learning classifiers and recognizing objects in the real world. A common problem that we face is that we require large amount of labeled data for this and at times the tasks we may work on may change. 

The paradigm of domain adaptation has burgeoned for solving this challenge using techniques that try generalizing the knowledge of previous tasks and models in Computer Vision has also been seen. The goal is to understand this application of Domain Adaptation through research publications in leading conferences in the field of Computer Vision.

Some of the tasks we will be going through would be ranging from to computer vision, ranging from image classification, semantic segmentation, object detection, face recognition, person re-identification, video understanding and 3D reconstruction.

## List of Papers
## 1. Divergence-based Domain Adaptation
### [a] MMD - Maximum Mean Discrepancy
- Learning Transferable Features with Deep Adaptation Networks [[Paper](https://arxiv.org/abs/1502.02791)] [[Review](https://github.com/tarujg/domain-adaptation-papers/blob/master/reviews/deep-adaptation-network.md)]
	- Mingsheng Long, Yue Cao, Jianmin Wang, Michael I. Jordan. ICML'15 
- Deep Transfer Learning with Joint Adaptation Networks [[Paper](https://arxiv.org/abs/1605.06636)] [[Review](https://github.com/tarujg/domain-adaptation-papers/blob/master/reviews/joint-adaptation-network.md)]
	- Mingsheng Long, Han Zhu, Jianmin Wang, Michael I. Jordan. ICML'17
- Unsupervised Domain Adaptation with Imbalanced Cross-Domain Data [[Paper](https://ieeexplore.ieee.org/document/7410826)] [[Review](https://github.com/tarujg/domain-adaptation-papers/blob/master/reviews/imbalanced-cross-domain.md)]
	- Tzu-Ming Harry Hsu, Wei-Yu Chen, Cheng-An Hou, Yao-Hung Hubert Tsai, Yi-Ren Yeh, and Yu-Chiang Frank Wang, ICCV '15

### [b] CORAL - Correlation Alignment
- Minimal-Entropy Correlation Alignment for Unsupervised Deep Domain Adaptation [[Paper](https://arxiv.org/abs/1711.10288)] [[Review](https://github.com/tarujg/domain-adaptation-papers/blob/master/reviews/min-entropy-coral.md)]
	- Pietro Morerio, Jacopo Cavazza, Vittorio Murino. ICLR'18 

### [c] CCD - Contrastive Domain Discrepancy
### [d] Wasserstein metric

## 2. Adversarial-based Domain Adaptation
### [e] Generative
- GANs
### [f] Non-generative
- DANN
- ADDA
    
## 3. Reconstruction-based Domain Adaptation
### [g] Encoder-Decoder
- DRCN - Reconstruction Classification
- DSN - Domain Separation
### [h] Generative based approaches

### Resources
1. [Tutorial on Transfer learning & Domain adaptation](https://www.youtube.com/watch?v=MIsSuWsZtKE)
