
External Links
- https://chatgpt.com/c/66e1750c-8a34-8000-904a-8c789bf1cf79
- https://paperswithcode.com/method/triplet-loss
- https://en.wikipedia.org/wiki/Triplet_loss
- https://habr.com/ru/articles/737060/

Siamese Networks

Similarity function
- Вычитание двух векторов эмбедингов и взятие нормы вместо косинусного расстояния.

Margin parameter
- Model pushes the dissimilar items further away by at least this margin

Challenges
- Triplet Selection (Hard Negative Mining)
- Margin Selection

Choosing triplets
- Если мы выбираем их рандомно, то это становится слишком легкой задачей