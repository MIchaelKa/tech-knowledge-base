
Connectionist Temporal Classification
CTC loss

# External Links

**Paper**
Connectionist Temporal Classification: Labelling Unsegmented Sequence Data with Recurrent Neural Networks
A. Graves et al.
[https://www.cs.toronto.edu/~graves/icml_2006.pdf](https://www.cs.toronto.edu/~graves/icml_2006.pdf)

**PaddleOCR**
https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.6/doc/doc_en/ppocr_introduction_en.md

**PyTorch**
https://pytorch.org/docs/stable/generated/torch.nn.CTCLoss.html

---

**learnopencv**
https://learnopencv.com/optical-character-recognition-using-paddleocr/

*CTC loss is responsible for training the network **as well as the inference** that is decoding the output tensor.*

# Вопросы

Какой лосс мы можем применить к sequential data?
Просто сумма CEL?

# Блоги

**An Intuitive Explanation of Connectionist Temporal Classification**
https://towardsdatascience.com/intuitively-understanding-connectionist-temporal-classification-3797e43a86c

*it tries all possible alignments of the GT text in the image and takes the **sum of all scores***

# Distill

**Sequence Modeling With CTC**
[https://distill.pub/2017/ctc/](https://distill.pub/2017/ctc/)

*There are challenges which **get in the way of us** using simpler supervised learning algorithms.*
мешают нам

*CTC works by summing over the probability **of all possible alignments** between the two.*


What if no one **possible alignment** was found?
What of we get **invalid** alignment?
Мы всегда можем составить такой **alignment**, просто возможно он будет обладать низкой вероятностью (иметь низкий скор) Мы всегда можем составить такую последовательность так как на каждом этапе можем выбирать из всех возможных символов доступного алфавита.

We allow any alignment which maps to Y after **merging repeats** and removing **blank** **tokens

**Blank token**
Необходимо иметь blank token
pseudo-character
Не нужно путать с обычным пробелом

**Inference**
One heuristic is to take the most likely output at each time-step. This gives us the alignment with the highest probability.
However, this approach can sometimes miss easy to find outputs with much higher probability.
Single output can have many alignments.
We can use a modified **beam search** to solve this.

**Алгоритм**
[[Dynamic Programming]]
[[Beam Search]]
