
ImageNet 1K vs 22K
ImageNet-V2

# Summary

**Size**
More than 14 million images

# External Links

wiki
[https://en.wikipedia.org/wiki/ImageNet](https://en.wikipedia.org/wiki/ImageNet)


**YK**
Do ImageNet Classifiers Generalize to ImageNet? (Paper Explained)
https://www.youtube.com/watch?v=fvctpYph8Pc

# Posts

**ImageNet 1K vs 22K. Any experts here to help figure this out?**
[reddit](https://www.reddit.com/r/MachineLearning/comments/3f9drh/imagenet_1k_vs_22k_any_experts_here_to_help/)


> **Mutual exclusiveness.** ImageNet is a hierarchy and therefore not all classes are mutually exclusive. Should an example classified as dog be punished because the training label states dalmatian? And how do you properly evaluate a classifier trained on a hierarchy of classes? Miss classification, hierarchy error, or something else?

> **Label exclusiveness** is in my opinion a general issue of ImageNet, as the dataset is clearly multi-label, while each image only has 1 label annotated. **The accepted work-around is to report the top 5 error**, but the network is still trained on the assumption that each image really displays only 1 category (which is generally false, e.g. a picture of tennis ball can also show tennis racket, person, net, tennis field etc.).

