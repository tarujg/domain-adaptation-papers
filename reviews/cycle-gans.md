# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks

Jun-Yan Zhu and Taesung Park, Phillip Isola and Alexei A. Efros, ICCV ‘2017

## Summary

This paper attempts to work on the unsupervised image translational problem and transforms images from source to target domain. Unlike the methods relying on paired images in both domains such as pix2pix it does not rely on one-to-one mapping between the domains. Mapping functions are learnt from one domain to another and vice-versa. Adversarial losses ensure that the mapped samples from one domain belong to the distribution of the other domain. Additionally, when a sample is mapped to the other domain and remapped back to same domain in a cycle, cycle consistency loss ensures that the content is unchanged even in the intermediate domain by reducing the space of possible mapping functions.

## Strengths

- The key advantage of this approach is that it does not need paired data unlike pix2pix methods and can work in the unpaired setting and provide good results as there is a lack of paired data in most real world scenarios.
- It translates the domain effectively based on the unpaired separation assumption that utilizes the adversarial loss stating that changing the style is easier.
- It also greatly works in the case where the cycle consistency loss preserves the content that is easy to maintain and complements adversarial loss.
- It is not task-dependent and has extensive experiments showing the working and generalization of the approach on a wide variety of tasks and use cases.
- Mode collapse is avoided because it may not satisfy cycle consistency ensuring easier training of the GAN models.

## Weakness
- Controlled transfer of the images is not done always and there maybe need of a regularization term to provide some kind of weak semantic supervision as it captures only pixel-level  differences. Shows poor performance in case of two significantly different objects in shapes, failing to capture high-level shared semantics
- Relies on GANs which have less reliability for certain tasks and the lack of understanding relations between different domains is there, neglecting the information between the images.
- The mapping function is deterministic. So, the mapping function can over-fit to represent non-naturally occurring pairings.

## Critique of experiments
- There are ablation studies showing the complimentary nature of two types of losses, where adding either one is not very helpful as compared to adding both. 
- Experiments show that CycleGAN is closer to the upper bound results provided by pix2pix than any other method.
- Style transfer and season transfer tasks show visually pleasing results while maintaining requisite properties.
- Quantiative results are demonstrated on photo to label task on CityScapes dataset and AMT real vs fake test on Google Maps  suggest the images are photo-realistic allowing real-world applications.

## Possible extensions
- Extension to videos by imposing stronger constraints on temporal relations to obtain smooth output videos 
- Adding different types of noise to generators to ensure a conditional distribution is learnt. 
- Application to other fields such as NLP, music style transfer etc. where unpaired training data is available 
- Multi domain mapping with cross cycle consistency across different combinations of domains.
