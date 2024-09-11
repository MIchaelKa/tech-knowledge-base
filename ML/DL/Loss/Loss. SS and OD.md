
Moved
https://www.notion.so/Losses-for-semantic-segmentation-and-object-detection-46ca9534a2b443718d3b8660bd4e4991

Losses for semantic segmentation and object detection

# External Links

https://www.jeremyjordan.me/semantic-segmentation/

Реализация различных лоссов и метрик
https://github.com/qubvel-org/segmentation_models.pytorch

# Links

[[Semantic Segmentation]]
[[Object Detection]]

[[Metrics. SS and OD]]

# Discussion

SS vs. OD
- Можно ли брать лоссы для сегментации и применять для детекции?
- IoU based measures
- В статье идет разделение на лоссы для сегментации и детекции
- https://www.linkedin.com/pulse/in-depth-exploration-loss-functions-deep-learning-kiran-dev-yadav/

Class imbalance in object detection
- Hard Negative Mining vs. Focal Loss
	- https://chatgpt.com/c/66e1e29a-d51c-8000-9005-b3a354b2d702
	- Manual vs. Automatic

# Detection

loss object detection

od_sanbox
- https://github.com/MIchaelKa/od_sandbox/blob/main/criterion.py


Multibox loss
- https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Object-Detection
- SSD
- Smooth L1
	- smoothed-L1 loss
	- The localization loss is the averaged Smooth L1 loss between the encoded offsets of positively matched localization boxes and their ground truths.
- Hard Negative Mining
- Multibox loss = L1 (only for matched boxes(priors) with GT) + (CE + HNM)

[[Focal Loss]]

[[IoU Losses]]


# Segmentation

Losses
- CEL
- Jaccard
- DiceLoss
- BoundaryIOU

[[UNet]]
- Meanwhile, Ronneberger et al. (U-Net paper) discuss a loss weighting scheme for each pixel such that there is a higher weight at the border of segmented objects.

CrossEntropyLoss vs. DiceLoss
- В DiceLoss не используется log для предикта, можно ли не использовать его также в CrossEntropyLoss?
- log_loss parameter
	- https://github.com/qubvel-org/segmentation_models.pytorch/blob/main/segmentation_models_pytorch/losses/dice.py

Implementation XEDiceLoss
- https://www.drivendata.co/blog/detect-floodwater-benchmark/


## Tversky Loss
tversky loss iou
tversky loss object detection
Focal Tversky loss

[https://habr.com/ru/companies/ods/articles/488852/](https://habr.com/ru/companies/ods/articles/488852/)

Tversky index
[https://en.wikipedia.org/wiki/Tversky_index](https://en.wikipedia.org/wiki/Tversky_index)


## Dice loss

IoU based measures

Links
- https://drivendata.co/blog/detect-floodwater-benchmark/
- https://en.wikipedia.org/wiki/Sørensen–Dice_coefficient

CEL vs. DICE
- https://stats.stackexchange.com/questions/321460/dice-coefficient-loss-function-vs-cross-entropy
- CEL
	- gradients are nicer
- DICE
	- similar on target metric
	- performs better at class imbalanced problems by design

 F1 score
- vs. F1 score
- `1 + beta ** 2`
	- look at mlcourse lecture for explanations
	- or wiki https://en.wikipedia.org/wiki/F-score
	- vs. Tversky Loss

Why by default the dice coefficient is not differentiable? How to make it differentiable?
- Когда мы считаем метрику мы должны получить из вероятности (вещественное число от 0 до 1) значение класса (0 или 1) и затем применить формулу для дайса или джакарда.
- Если мы считаем лосс, то должны использовать вероятности вместо дискретных значений
- Дайс и джакард с препиской софт

Сlass imbalance
- Как дайс борется с дисбалансом классов?

Why it range from 0 to 1?
- Find pictures in your notebook!

Low-confidence predictions
- we are essentially penalizing low-confidence predictions
	- in numerator
	- ??
	

## BoundaryIOU

Paper
https://arxiv.org/abs/2103.16562

https://chatgpt.com/c/437c422d-07e1-40b8-869c-ed148b1b09d4

Steps
- Boundary Extraction
- IoU is calculated specifically for these boundary pixels

Mask IoU
- This measure values all pixels equally and, therefore, is less sensitive to boundary quality in larger objects
- Mask IoU loss vs. Jaccard loss
	- тоже самое что обычный IoU или Jaccard?
	- No Practical Difference