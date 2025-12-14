
CEL == Xent

# External

https://www.notion.so/Cross-Entropy-Loss-75cb7ea3fb8b4da3999a79dcc7d8143c

https://pytorch.org/docs/stable/generated/torch.nn.CrossEntropyLoss.html

https://ml-cheatsheet.readthedocs.io/en/latest/loss_functions.html

# Links

[[Softmax]]

# BCEWithLogitsLoss

BCEWithLogitsLoss
https://pytorch.org/docs/stable/generated/torch.nn.BCEWithLogitsLoss.html#torch.nn.BCEWithLogitsLoss

pos_weight
- trade off recall and precision
- It’s possible to trade off recall and precision by adding weights to positive examples. In the case of multi-label classification the loss can be described as ...
- p ​>1 increases the recall, p < 1 increases the precision.
- https://chatgpt.com/c/689efda7-147c-8329-ad39-d23f2eddccb4