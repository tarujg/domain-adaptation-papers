# Joint Distribution Optimal Transportation for Domain Adaptation

Nicolas Courty, Rémi Flamary, Amaury Habrard, Alain Rakotomamonjy, NIPS ‘2017
 

## Summary

This paper targets unsupervised domain adaptation by using “optimal transport” to measure the distances between distributions. To align the feature and label distributions it incorporates the Wasserstein metric by jointly targeting the shifts in the marginals and the class-conditional distributions.

The key contributions are:
- It minimizes the joint distributions of source and target, while simultaneously finding a nonlinear transformation for an input.
- It provides an efficient algorithm for optimization as it seeks to minimize the bound on target error.
- The approach is not restricted and can handle a wide range of loss functions and networks and works with both regression and classification tasks.

## Strengths

- Does a single step adaptation by use of a modified cost function rather than adapting the representation and learning a classifier on top of that.
- Finds the joint distribution which is more representative and a richer representation that can be utilized for auxiliary tasks as well.
- It provides a wide range of options for using different loss functions and models or networks (ranging from SVMs, NNs, etc.)
- The method also has an optimized solution for optimization that has guarantees for convergence as well.

## Weakness
- This approach doesn’t scale well for large datasets as it the optimization objective consists of solving for values which depend on a matrix with dimensions Ns x Nt (Ns: # source and Nt: # target) for each iteration.
- In the cost function there is an L2-metric being used which may not appropriately represent the alignment between the source and target sample.

## Critique of experiments

- Experiments were carried out on the Caltech-Office dataset for classification, Amazon reviews dataset for classification,Wifi localization dataset for regression.
- JDOT does not outperform OT based approaches for the all tasks in the Caltech-Office dataset and fails to include JAN and other state-of-art approaches which perform well on the Office-31 dataset.
- For the task on Amazon reviews JDOT has the ease in the parameter setting unlike other DANN and also provides good results on most tasks with the Hinge Loss giving better results that MSE, which confirms the efficacy of the Hinge loss on classification.
- For the transfer across devices task in Wifi localization regression, this approach significantly outperforms outer method that shows that optimal transport can allow higher distribution variation unlike other discrepancy methods.

## Possible extensions
- The alignment can be done for the Convolutional features and not just the DeCAF6 layer as mentioned in the paper.
- The method can be extended to multi-domains scenarios possibly as well.
- Can possibly use a different representation for alignment as opposed to the L2 distance in the image space.
