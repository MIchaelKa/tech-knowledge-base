
Энтропия
Энтропия Шеннона

Entropy, Cross-Entropy and KL-Divergence

# External 

Notion
- https://www.notion.so/92f61ef05ddc4a94a043a9d6ddd60768


# Videos


A Short Introduction to Entropy, Cross-Entropy and KL-Divergence
- https://www.youtube.com/watch?v=ErfnhcEV1O8
- Intro
	- To transmit one bit of information is the same as reduce the recipient's uncertainty by the factor of 2.
		- Example: Initially you had 2 equally likely events, now you have only one 100% event.
	- Number of bit needed is the binary log of uncertainty reduction factor (number of states)
		- $log_2(8) = 3$
	- Uncertainty reduction is the inverse of the event's probability
		- Information gain
		- $log_2(4) = log_2(1/0.25) = log_2 1 - log_2 0.25 = - log_2 0.25 = 2$
			- Uncertainty reduction is 4
			- Number of bit needed is the minus of binary log of probability of event
- Entropy
	- If we have different probabilities for events (0.75 and 0.25), how much information you get on average?
	- $-(0.75 * log_2(0.75) + 0.25 * log_2(0.25))$
	- $H(p) = -\sum_{i}p_i*log(p_i)$
	- Tells how much information on average we get from one sample drawn from probability distribution *p*. It tells how unpredictable your distribution is.
- Cross-Entropy
	- Average message length
		- message length - log of predicted probability
		- When we sending 2bit message for certain event we are implicitly assuming that this event has probability of 0.25
	- На этом месте рассматривается похожая проблема, как однозначно расшифровать последовательность из нулей и единиц, как в книге Шеня и Верещагина - Теория Множеств.
	- When we sending 2bit message for certain event we are implicitly assuming that this event has probability of 0.25
	- $H(p,q) = -\sum_{i}p_i*log(q_i)$
		- p - true distribution
		- q - predicted distribution
	- When p equals q then Cross-Entropy equals Entropy. If they different then Cross-Entropy is larger by some amount.
- KL Divergence
	- Relative entropy
	- is the difference between Entropy and Cross-Entropy
	- $D_{KL}(p||q) = H(p,q) - H(p)$
- Cross Entropy Loss
	- [[Cross Entropy Loss (CEL)]]
	- $ln(p) \quad \textrm{or} \quad log(p) \quad \textrm{instead of} \quad log_2p$
	- p - all zeros except one true label
	- CEL - negative log of estimated probability for the true class (no sum)

KL Divergence
- Kullback-Leibler Divergence
- https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence
- Расстояние Кульбака — Лейблера
- ru.wikipedia.org/wiki/Расстояние_Кульбака_—_Лейблера


The KL Divergence : Data Science Basics
- https://www.youtube.com/watch?v=q0AkK8aYbLY
- Our metric needs to be asymmetric