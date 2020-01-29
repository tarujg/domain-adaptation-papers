# Unsupervised Domain Adaptation with Imbalanced Cross-Domain Data

Tzu-Ming Harry Hsu, Wei-Yu Chen, Cheng-An Hou, Yao-Hung Hubert Tsai, Yi-Ren Yeh, and Yu-Chiang Frank Wang, ICCV, 2015

## Summary

This work targets the problem of unsupervised domain adaptation with imbalanced data and particularly it explores the issues arising due to intra-domain and intra-class variations. It solves feature space learning of the latent sub-domains in the underlying data and simultaneously performing instance reweighting. It tries to minimize a domain-dependent MMD accounting for the label and latent-domain information.

Its main contributions are:
- It aligns the conditional distributions through the Closest Common Space Learning (CCSL) algorithm proposed.
- It utilizes label and structural cues within and across different domains by incorporating a latent domain variable and reducing the importance of irrelevant instances of the source domain.
- It provides better cross-domain classification results for imbalanced cross-domain datasets, empirically.

## Strengths

- As the computation of the similarity matrix is computationally expensive, the paper employs the use of a lower-dimensional empirical kernel mapping for the optimization procedure.
- A large variety of datasets can be combined due to the underlying assumption of the latent decomposition of the data into various sub-domains and this leads to better performance due to the labels being present.
-  CCSL minimizes a domain-dependent MMD based on the joint distribution by combining a cross-domain marginal distribution and a term with both label and latent-domain information.

## Weakness

- There is no consideration of different class weight bias in this as CCSL mainly combines MMD with the domain-dependent MMD.

## Critique of experiments

- Experiments were carried out on the MNIST and USPS (for digit recognition) and used pixel intensities as features, and Caltech-256 and Office-31 (for object recognition) with a 4096-dimensional feature vector based on DeCAF6.
- In comparison with existing methods for classification with balanced cross-domain data, CCSL produced comparable results unless a method didn’t use label information. It also performed well particularly for large target domain sizes due to proper data adaptation metrics.
- For classification with imbalanced label numbers, where the source domain is larger than the target domain, CSSL showed improved performance over MMD-based approaches as they assumed data balance across domains.
- For classification with mixed-domain data, CSSL didn’t significantly outperform as imbalanced label numbers is a harder problem to solve.

## Possible extensions
- There could be some more exploration done for kernel functions as the paper just suggested the use of linear kernels. A lot of the works use more complex functions to provide more richness of functions for matching distributions.
- Since the methodology is computationally expensive there could be a method employing the usage of a linear-time unbiased estimate of the MMD calculations.
- CSSL is an instance selection method as shown, while there is a possibility of a feature-based approach.
