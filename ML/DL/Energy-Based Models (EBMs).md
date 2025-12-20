

# External

https://uvadlc-notebooks.readthedocs.io/en/latest/tutorial_notebooks/tutorial8/Deep_Energy_Models.html

https://www.reddit.com/r/MachineLearning/comments/kc8ruw/d_what_exactly_is_yann_lecuns_energy_based/

# Materials

NYU-DLSP20
- https://atcold.github.io/NYU-DLSP20/en/week07/07-1/
- https://www.youtube.com/watch?v=tVwV14YkbYs&t=64s
- 2020
- softmax over images
	- vs. over pixels
	- impossible since infinite? very large number of possible images
	- large sample space
- FFN
	- explicit function
	- finite number of output
	- what if we want to predict a picture?
- energy function
	- implicit function
	- why it's called energy?
	- describes the level of dependency between (x,y) pairs
	- used in inference, not in learning
	- minimize during inference
		- start with some random y
		- use gradient descent
	- datapoints should be always in valleys (low energy)
- implicit vs. explicit function
	- example of implicit function from calculus: circle
- Segmentation example
	- think about segmentation problem
	- GD in segmentation image space vs. classic segmentation
- Latent variables
	- boundaries of letters
- Connection with probabilistic modeling
	- scores - because this is not normalized probability
	- from energy to probability
		- Gibbs-Boltzmann distribution
			- https://en.wikipedia.org/wiki/Boltzmann_distribution
			- *The distribution shows that states with lower energy will always have a higher probability of being occupied.*
		- using exponent again!
			- my old question!
			- why we need exponent if all we need is to sum distribution to one?
		- classical statistical physics
		- beta parameter - similar on how temperature in CEL work
		- getting p(y|x)
	- We can look at the energies as unnormalised negative log probabilities
		- Why log?
			- Plug to formula and see
- Marginalizing over the latent variable
	- E -> F
	- F - free energy
- Contrast function
	- ?
- SSL
	- Why masking not works well for images?
		- [[DINO]]
		- images vs. text
			- text (words) is discrete
			- images are continues
	- Example why having latent variable is important for video frames prediction
		- Helps with blurry results!
- Training EBM
	- Why probabilistic methods break state that F is smooth?
	- Contrastive methods
		- [[CLIP]]
		- 


The new contender to GANs: score matching with Langevin Sampling
- https://ajolicoeur.ca/the-new-contender-to-gans-score-matching-with-langevin-sampling/
- DSM-ALS
- convergence guarantees (i.e., no mode collapse)
- (Annealed) Langevin Sampling




