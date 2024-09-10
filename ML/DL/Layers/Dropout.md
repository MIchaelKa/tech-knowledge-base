
Moved
https://www.notion.so/Dropout-8f1b9d8a912340a6a216a38574cb69c3


# External Links

https://cs231n.github.io/neural-networks-2/#reg

# Overview

While training, dropout is implemented by only keeping a neuron active with some probability p

Longer to train since we are updating only part of the network?

Interpretations
- Forces the network to have a redundant representation
- Another interpretation: Dropout is training a large ensemble of models. Each binary mask is one model trained on one datapoint

Implementation
- Need to adjust at test time.
- Better use Inverted Dropout (do scaling at training time)