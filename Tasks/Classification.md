

softmax vs. sigmoid
- https://stats.stackexchange.com/questions/233658/softmax-vs-sigmoid-function-in-logistic-classifier
- softmax vs. sigmoid for one class classification in the last layer
- softmax gives the same probabilities when number of classes K = 2


# Multi Label

мульти-лейбл
multi-label classifier

WPIE

https://en.wikipedia.org/wiki/Multi-label_classification

https://machinelearningmastery.com/multi-label-classification-with-deep-learning/

In summary, to configure a neural network model for multi-label classification, the specifics are:
- Number of nodes in the output layer matches the number of labels.
- Sigmoid activation for each node in the output layer.
- Binary cross-entropy loss function.