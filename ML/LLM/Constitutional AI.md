
Constitutional AI: Harmlessness from AI Feedback
https://arxiv.org/abs/2212.08073

Anthropic RL-CAI & RLAIF

RL from AI Feedback (RLAIF)

[[RLHF]] -> RLAIF

gonzo_ML
- https://t.me/gonzo_ML/1285
- Звучит сингулярненько
	- Singular
- Scaling Supervision
- RLHF недостатки
	- десятки тысяч человеческих оценок не позволяют пролить свет на суть training objective, потому что это сложно понять и суммаризовать
	- Goal misgeneralization
		- TODO
- файнтюнить AI модели на предмет безвредности (harmless) планируется с помощью конституции, содержащей порядка десятка простых принципов, выраженных человеческим языком
- есть серьёзный конфликт между полезностью (helpfulness) и безвредностью (harmlessness)
- авторы продолжают использовать человеческий фидбек для helpfulness, но переходят на AI фидбек для harmlessness.
- Два этапа
	- (Supervised Stage) Critique → Revision → Supervised Learning.
	- (RL Stage) AI Comparison Evaluations → Preference Model → Reinforcement Learning.
- Supervised Stage
	- модель просят покритиковать эти ответы в соответствии с принципами (конституцией), а затем переписать их с учётом критики.
	- предобученная модель файнтюнится через обычный supervised learning на финальных ответах
	- результирующая модель фигурирует под именем SL-CAI
- RLHF
	- фидбек человека заменяется на фидбек AI модели
	- получают датасет предпочтений AI-модели для harmlessness
	- модель получается гибридная, она содержит человеческие оценки для helpfulness, и только машинные оценки для harmlessness
- Models
	- helpful RLHF
		- RLHF на человеческих оценках по helpfulness, не по harmlessness
		- (нет обучения на harmlessness)
	- helpfulness and harmlessness (HH) RLHF
	- SL-CAI
	- RL-CAI


