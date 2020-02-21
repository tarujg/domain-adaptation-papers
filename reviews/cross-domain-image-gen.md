# Unsupervised Cross-Domain Image Generation

Yaniv Taigman, Adam Polyak, Lior Wolf, ICLR ‘2017 

## Summary

This paper targets the unsupervised image translational method mapping the example from source to target. It however is different from pixel-to-pixel translation work in the field that it does not need training pairs from both the domains that are aligned. It breaks the problem particularly into learning a Generative function to be learnt into a representation into a feature space based on ConvNet for particular use case common for both the source and target and a decoding network that acts as a generator for target domain samples. 

The key contributions are:
- It proposes a f-constancy in an unsupervised manner for comparison of samples from different domains with a fixed function.’
- Penalizes the pixel-wise difference between target sample and the re-generated version of it.
- Provides significant results on transferring SVHN to MNIST and facial images to emoji styles.

## Strengths

- Proposed a Lconst loss to ensure that generated output is semantically close to input, L_tid to ensure that decoder is sample invariant to Target and uses a L_gan with a ternary discriminator.
- The paper has an end-to-end training method while also decomposition of generative function that is only used to transfer the sample into existing learned feature extractor along with a decoder gives significantly good results.
- The paper has extensive experiments with different loss functions included and excluded showing the importance of each of the proposed losses.

## Weakness
- Although the paper relies mainly on f-constancy, it does not provide a good method of finding a good f-function for both target and source and this may not always be the case.
- The process has to be repeated for domain adaptation between similar domains but different tasks and does not necessarily scale well.

## Critique of experiments
- Provides improved results on adaptation on SVHN to MNIST task by using a ConvNet to transfer to MNIST image style and then using a K-NN classifier significantly outperforming DANN and other approaches.
- For Zero Shot based experiments, they train a DTN from scratch by removing the digit 3 and show good generalization to show the importance of a good expert (f) as removal of f hurts the performance significantly. 
- As the main highlight, they transfer the faces to emojis and compare the results to human annotators, and the results are compared by showing retrieval metrics using facial recognition networks to show that the generated emojis are more similar and tend to keep the individuals distinctive visual features.

## Possible extensions
- It although restricts the use cases to very limited task domains and can be extended to show generality over domains such as texts and images and tasks like semantic segmentation for synthetic to real images like in autonomous driving. 
- Owing to the similarity between this work and CycleGANs there could be an incorporation of the Cycle-consistency loss to make the asymmetric mapping be learned from both domains. This could help in generating realistic faces from emojis.

