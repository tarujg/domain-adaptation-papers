# Domain Separation Networks

Konstantinos Bousmalis, George Trigeorgis, Nathan Silberman, Dilip Krishnan, Dumitru Erhan, NeurIPS ‘2016

## Summary

This method targets unsupervised DA with a Deep learning network that separates the representations for source and target domain into a private subspace (domain specific properties) and shared subspace (similar representations). This targets the shortcomings of existing approaches that work on underlying assumption of a shared representation between the domains only. Using existing DA approaches to make the shared representations similar along with soft subspace orthogonality constraints to make private and shared representations dissimilar. The experiments perform well on a variety of tasks and provide the shared and private representations and their visualizations to show the interpretability aspect of the DA task.

## Strengths

- Model trained to perform on the source domain task and with partitioned useful representations to reconstruct the images from both domains avoiding trivial solutions and to add generalizability and models what is unique to each domain with the help of a reconstruction loss.
- Private subspaces for each constituent domain that captures domain specific properties like low level image statistics helps in avoiding the shared-representation only approaches that are susceptible to noise contaminating the correlation of the shared distribution with the use of a difference loss enforcing subspace orgthogonality. Representations learned are unique are more appropriate for the task.
- Also encourages representations from both domain to be similar and useful irrespective of domain using the similarity losses like existing works.
- Enforce adversarial losses to minimize domain shift in a shared feature space, and augment model with private feature spaces with the dissimilarity loss between the shared and private spaces.

## Weakness
- DSN relies on adversarial training and is somewhat sensitive to the random initializations.
- All the experiments performed on the synthetic to real data domain transfer task and are not comprehensive enough for other tasks.
- This approach mainly works for the “low-level” differences in constituent domains.
- Model selection and hyper parameter tuning is tough because of 4 different loss terms and reverse validation is shown to perform poorly and labeled examples from target domain can’t be used.

## Critique of experiments
- Considers a variety of classification tasks such as MNIST to MNIST-M, SVHN to MNIST, synthetic to real traffic signs on GTSRB, synthetic LINEMOD objects with real world backgrounds for Pose estimation and classification that can be tailored based on task loss. 
- Provides ablation studies of orthogonality constraint, reconstruction losses and use of scale-invariant MSE as opposed to regular MSE to show importance of each novelty.
- Does a comparative reconstruction analysis showing original image, and its reconstructed form using the shared representations, private reconstructions and combined reconstructions showing the necessity of the private as well as shared representations.

## Possible extensions
- Hyper-parameter tuning is one of the key challenges when incorporating so many loss terms. Therefore, there can be more efforts put into this sphere of the work. 
- Due to the architecture style, we can try extending this to the scenario of multiple source domains as well by having different heads for each of the source domain.
- The similarity metric is flexible and can be explored with other methods like MMD and Joint-MMD like in JANs to create newer architectures. 

