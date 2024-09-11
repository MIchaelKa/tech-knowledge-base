
https://chatgpt.com/c/66e0dfb6-b878-8000-aa78-e9b318683d0a

Train on crops, infer on large images
- [[Crops]]

Ботлнек слой в реснете
- [[ResNet]]

Батчнорм
- До или после активации
- [[Network Topology]]
- [[Normalization]]
- [[Identity Mappings in Deep Residual Networks]]


# 1. Deep Learning Fundamentals

- What is backpropagation, and how does it work?
- Explain the concept of overfitting and underfitting in neural networks.
- What is the vanishing gradient problem, and how can it be addressed?
- What is the difference between a fully connected (dense) layer and a convolutional layer?
- Explain different types of activation functions (ReLU, Sigmoid, Tanh) and when to use them.
- What are dropouts and batch normalization, and why are they important?
- How would you implement gradient descent, and what are the differences between SGD, Adam, RMSprop, etc.?
- What are LSTMs and GRUs? When are they used in practice?
- Explain the difference between transfer learning and training a model from scratch.
- How would you handle imbalanced data in a deep learning model?

# 2. Computer Vision Deep Learning Fundamentals (CV DL Fundamentals)

- Explain the architecture of a Convolutional Neural Network (CNN).
- What is the role of pooling layers in CNNs, and what types of pooling are there?
- How do you handle different image sizes in CNNs?
- What is the difference between instance segmentation, semantic segmentation, and object detection?
- What are common losses for image segmentation and object detection models?
	- [[Loss. SS and OD]]
- How does a region proposal network (RPN) work?
- What is transfer learning in CV, and how would you fine-tune a pre-trained model?
- How do GANs (Generative Adversarial Networks) work, and what are some of their applications in CV?
- What is the role of data augmentation in training CV models?
- Explain the concept of attention mechanisms in the context of vision transformers.

# 3. Classical Computer Vision

- What are the differences between edge detection algorithms such as Sobel, Canny, and Prewitt?
- Explain how SIFT, SURF, and ORB work for feature detection.
- What is the role of the Hough transform in computer vision?
- How does optical flow work, and when would you use it?
- What is the epipolar geometry in stereo vision?
- How does the RANSAC algorithm help in model fitting?
- Explain the concept of homography and its applications in CV.
- How do you calibrate a camera and correct for lens distortion?
- What is background subtraction, and how is it used in video surveillance?
- What are the main differences between Haar cascades and modern machine learning-based detectors like SSD or YOLO?

# 4. Productizing DL/CV Solutions

- What are the main challenges when deploying a deep learning model in production?
- How would you optimize a deep learning model for real-time inference?
- How do you handle model versioning and updates in production environments?
- What techniques would you use to reduce the memory footprint of a deployed model?
- How do you monitor the performance of a DL model in production and detect when retraining is needed?
- What strategies would you employ to handle model drift?
- How would you ensure scalability for a DL solution used by millions of users?
- What are the best practices for logging and monitoring errors during inference?
- How do you manage edge cases or out-of-distribution data in a production system?
- What is A/B testing in the context of deploying ML models, and how would you use it?

# 5. Case Study

- You’re tasked with building an object detection system for a retail store. How would you approach the problem, including data collection, model selection, training, and deployment?
- How would you design a CV system for face recognition at an airport, ensuring scalability and privacy compliance?
- Imagine you need to develop a DL-based product recommendation system. How would you approach the feature engineering, model training, and deployment?
- You are tasked with detecting anomalies in images of industrial equipment. What steps would you take, and how would you evaluate your solution?
- Design a system to automate the quality inspection of products on a factory line using classical CV and DL techniques. How would you integrate both approaches?
- How would you build a solution to handle real-time video analysis (e.g., vehicle detection) using edge devices? What optimizations would be necessary?