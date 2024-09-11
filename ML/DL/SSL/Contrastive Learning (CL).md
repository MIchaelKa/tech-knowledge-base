
Moved
https://www.notion.so/Contrastive-Learning-d2ba9b890b464d6590cfe6ecf3075af5

# Внешние ссылки

[https://pytorch-lightning.readthedocs.io/en/latest/notebooks/course_UvA-DL/13-contrastive-learning.html](https://pytorch-lightning.readthedocs.io/en/latest/notebooks/course_UvA-DL/13-contrastive-learning.html)


# Ссылки

[[Metric Learning]]

[[CLIP]]

[[SimCLR]]
[[BYOL]]
MoCo

# Обзор

Contrastive loss
NT-Xent
InfoNCE loss

NT-Xent
- Normalized Temperature-scaled Cross Entropy Loss
- https://paperswithcode.com/method/nt-xent
- softmax operation over the similarity scores

InfoNCE
- Noise-Contrastive Estimation
- https://paperswithcode.com/method/infonce

CEL vs. NT-Xent
- CEL == Xent
- [[Cross Entropy Loss (CEL)]]
- [[Temperature]] parameter, why we need it?
- https://chatgpt.com/c/66e1722f-4378-8000-bd9c-82502f5ed46a

Contrastive loss vs. InfoNCE loss vs. NT-Xent
- https://chatgpt.com/c/66e1722f-4378-8000-bd9c-82502f5ed46a
- NT-Xent
	- A specific form of InfoNCE Loss that includes temperature scaling for better control over the distribution of similarities.


