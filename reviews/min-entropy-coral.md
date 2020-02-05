# Minimal-Entropy Correlation Alignment for Unsupervised Deep Domain Adaptation

Pietro Morerio, Jacopo Cavazza, Vittorio Murino, ICLR ‘2018
 

## Summary

This paper targets the unsupervised domain adaptation problem by combining the concepts of alignment of the geodesic correlation metric along with minimization of the entropy.  

Its main contributions are:
- Combines the usage of correlation alignment with the entropy minimization.
- It makes use of the geodesic distance as opposed to the Euclidean distances which doesn’t account for structural information.
- It provides a simplified approach for hyper parameter tuning using the entropy metric.
- It resulted in performed marginally better in image classification tasks and is easier to modify for the learning process.

## Strengths

- Provides an efficient geodesic log-Euclidean metric that is efficient to compute due to lack of matrix inversions to capture geometry of the data unlike a Euclidean metric.
- Actively targets model selection, which is troublesome for UDA problems, by considering a fully unsupervised scenario that reduces the entropy loss on the target.
- Also eases the learning process for back-propagation due to the elegant Minimal-Entropy Correlation Alignment metric that has a differentiable close-form expression.

## Weakness

- This approach outperforms other approaches which use pseudo-labels for the UDA problem. This would not scale well when we have labels for some portion of the target domain and do not use that efficiently in the given loss metric.

## Critique of experiments

- Experiments were carried out on SVHN to MNIST and SYN DIGITS to SVHN. Additionally, RGB images from NYUD data were used to perform cross-modal recognition on depth data.
- This paper lacks results on the datasets such as MNIST-USPS and larger datasets such as Caltech-256 and Office-31 which would give more concrete evidence for the proposed methodology.
- Based on experiments between domains that are similar with aligned source and target distributions, other methods outperform the existing method. However, when this is not the case, MECA outperforms existing approaches.
- On both the adaptation processes the FC layer where the covariance computation is done is reduced in size for performance related reasons.

## Possible extensions
- For the correlation metric for each source and target we can do some kind of weighting for class balancing across both source and target domains to remove the bias of different class sizes.
- We can try aligning the geodesic correlation metric for multiple FC-layers in a DAN or JAN kind of an approach. At the expense of compute, we might get richer and better alignment.
- There can be extensive results for other UDA datasets for showing more concrete support for the argument.

