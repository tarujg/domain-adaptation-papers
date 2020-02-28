# InfoGAN: Interpretable Representation Learning by Information Maximizing Generative Adversarial Nets

Xi Chen, Yan Duan, Rein Houthooft, John Schulman, Ilya Sutskever, Pieter Abbeel, NeurIPS ‘2016

## Summary

InfoGANs extend the ideas of GANs to learn disentangled representations which are more interpretable. The latent noise vector used to generate samples is decomposed into controlled parts that express salient semantic features and a noisy vector to generate more controlled samples. Using both discrete and categorical latent variables we can generate a variety of controlled images. The network achieves this by maximizing the mutual information between the meaningful part of the latent vector and the generated sample that is also dependent on the noise vector. This mutual information is thought of as a regularizing part for the original GAN optimization objective.

## Strengths

- Learns meaningful and intuitive disentangled in completely unsupervised fashion
- Easily added to existing GAN architectures with a minimal extra computed loss term with an extra decoder head to the network predicting code from the generated sample.
- Mathematical proofs provided for lower bound to mutual information that approximates posterior distribution via a neural network based auxiliary distribution based on variational information maximization.
- Uses a re-parameterization trick to such that sampling from a user-specified prior (works well for categorizable data) instead of the unknown posterior.
- It has an extra hyper-parameter that is easily tunable and simply using the value of 1 produces good results.

## Weakness
- The given variational bound on the mutual information ignores the H(c) term that is an oversimplification and may hinder the power of the methodology.
- The paper fails to show experiments quantitative differences for the method and lacks ablation studies.
- The paper carries extensive experiments showing variation of only one term and observing its effects and not two at a time to show combined effects.
- This has most of the issues that we experience with most GAN architectures.

## Critique of experiments
- The 10-discrete codes along with continuous variables learnt different digit values based on prior information for MNIST showing that the discrete code changed the generated digit and continuous code varied the tilt and width for a wider range than trained for initially. The comparison with vanilla GAN where varying codes showed no meaningful or consistent change.
- Similar experiments were run on SVHN, Faces, and Chairs datasets showing that there was a variation on a variety of domain-based semantic features by varying the latent codes.
- Experiment on the CelebA dataset showed that the disentangled representations were learned as a different pose, emotion, hairstyle and pair of glasses.

## Possible extensions
- Approach can try using a more expressive term instead of simplified approximation on the mutual information approximation.
- This methodology can try learning more hierarchical representations such as in Capsule Networks.
- We can try doing domain adaptation for a down-stream task that actually motivated the paper in the first place.
