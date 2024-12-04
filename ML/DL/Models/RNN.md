
Backpropagation through time

# External

Char-level RNN
- https://pytorch.org/tutorials/intermediate/char_rnn_classification_tutorial.html
- https://colab.research.google.com/drive/1tZA3-tqj2e9JDogUeV2wuBCut4jC3xBE

pytorch
- https://pytorch.org/docs/stable/generated/torch.nn.RNN.html

# Questions

RNN Training and hidden state
- https://chatgpt.com/c/674ed00c-8bfc-8000-9b1a-5b14c536581f
- you need to manage the hidden states for each sequence in the batch
- in pytorch forward method returns hidden state for each element in the batch

RNN slow training
- Sequential likelihood evaluation (very slow for training)
	- cs236
- https://chatgpt.com/c/674f03a7-1714-8000-ae3d-a8f17524c074
- Vanishing/Exploding Gradients in RNNs