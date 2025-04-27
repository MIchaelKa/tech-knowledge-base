
# Links

[[Soft Labels]]
[[Active Learning]]

# External

soft pseudo labels
https://www.kaggle.com/c/rfcx-species-audio-detection/discussion/220760

Forum discussion
https://community.drivendata.org/t/pseudo-labeling-during-8-hours-of-inference/6427

AV
https://www.analyticsvidhya.com/blog/2017/09/pseudo-labelling-semi-supervised-learning-technique/

# Terms

QDA


# Overview

v1
- https://chatgpt.com/c/df1920dd-9b9d-4e10-ab04-648cf516f6bc
- Select high-confidence predictions as pseudo labels for the unlabeled data.

v2
- Pseudo Labeling - QDA
- [https://www.kaggle.com/cdeotte/pseudo-labeling-qda-0-969](https://www.kaggle.com/cdeotte/pseudo-labeling-qda-0-969)
- Pseudo labeling is the process of adding confident predicted test data to your training data.

Pseudo-labeling and soft labels
- https://chatgpt.com/c/67af32f5-af2c-8000-9c68-5676fa6381e7
- https://chatgpt.com/c/67dc34be-4db8-8000-a2c7-2135b1f2eab2
- [[Pseudo Labeling]]
- BCEWithLogitsLoss is ok
- CrossEntropyLoss and KLDivLoss
- Confirmation bias
	- Confirmation bias in pseudo-labeling occurs when the model reinforces its own errors
- Training on TP and FP