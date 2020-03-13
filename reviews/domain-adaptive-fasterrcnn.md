# Domain Adaptive Faster R-CNN for Object Detection in the Wild
Yuhua Chen, Wen Li, Christos Sakaridis, Dengxin Dai, Luc Van Gool, CVPR ‘2018

## Summary

The method proposes an end-to-end model targeting UDA for Object Detection. It targets the domain shift both for image level (style, illumination) and instance level (object appearance, size) based on H-divergence theory. These are done on the Faster-RCNN network where a domain classifier learns robust domain-invariant features using adversarial training. Simultaneously, consistency regularization is used to learn classifiers at various levels for domain-invariant region proposal network (RPN).

## Strengths

- The work provides significant theoretical perspective in a probabilistic framework for cross-domain object detection.
- It seems to be more tolerant to the diverse scale changes as opposed to standard Faster R-CNN which has a significant performance reduction. This is because scale change is global, which affects all instances and background and is solved by image-level alignment.
- It integrates the domain adaptation components into the Faster R-CNN framework with training in an end-to-end fashion. 
- Targets the domain-shift problem at the image level and the instance level and also provides an approach to make the RPN to be domain invariant through a regularizer.

## Weakness
- There should have been a comparative analysis with other state-of-art object detection networks.
- The lambda trade-off parameter in the network is scenario dependent and can be difficult to tune.

## Critique of experiments
- When learning from synthetic data, training data is SIM 10k (GTA5), with Cityscapes as target domain. The experiments uses only the car objects for detection. Improvement is seen with both image-level adaptation only, instance-level alignment only showing reduction in domain shift using both. And by combining them there is a further improvement showing domain shift on both levels. Lastly, there is further improvement using the consistency regularization terms showing significant boost over Vanilla RCNN.
- For driving in adverse weather, training data is Cityscapes with different instance annotations, target data in foggy weather is foggy Cityscapes datasets. Confirms the performance improvements from synthetic data scenario, while also showing generalization across categories, as it reduces domain discrepancy across different object classes.
- For cross camera adaptation, where the training data and test data are captured with different camera setups (KITTI and Cityscapes). The method scales well for both tasks, i.e., K → C and C → K.
- Additional error analysis of accuracies of most confident detections are used to show that image-level or instance-level adaptation both improve the number of correct detections and significantly reduces the number of false positives. Also, image only alignment has lesser background error possibly due to improvement in RPN as it gives region proposals with better localization performance.

## Possible extensions
- We can try utilizing this idea in the case of a semi-supervised label setting or few-shot learning scenarios.
CycleGAN can used for image-to-image translation where for pixel-level adaptation. We can train the network on datasets images from PASCAL VOC translated to other domains, and then train images on domain adapted images.
- The methodology has the scope to be extended to the scenario when there are multiple domains present, where-in we can have a slightly more complex similarity metric with multiple CNN heads corresponding to each domain.
