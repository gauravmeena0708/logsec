- Measure of How one probability distribution is different from a second, reference distribution.
- **Measure of difference between two distributions**
- X = {x1, x2, x3...xn} -> diff between $p_{\theta}\left(X_1\right)\&q_{\phi}\left(x1\right)$
- As probabilities are very small and which will need to be multiplied with other small numbers... we take log of the same hence we want the average/expected difference between p and q
	- Parts
		- $\log P\theta-\log Q\phi$
		- llikelihood ratio = $\frac{p_{\theta}(x)}{q_{\phi}(x)}$
		- log likelihood ratio $log \frac{p_{\theta}(x)}{q_{\phi}(x)}$ -> it is function of random variable
		- Weighted log liklihood ratio $p_{\theta}(x)\log\frac{p_{\theta}(x)}{q_{\phi}(x)}$
	- Expected Value of log Likelihood ratio
		- For continuous variable $\int p_{\theta}(x)\log\frac{p_{\theta}(x)}{q_{\phi}(x)}\,dx$
			- In this-> Self information $p_{\theta}(x)\log p_{\theta}(x)$
			- Cross entropy $p_{\theta}(x)\log q_{\phi}(x)$
		- For Discrete variable $\sum_{x}p_{\theta}(x)\log\frac{p_{\theta}(x)}{q_{\phi}(x)}$
	- Issue
		- The integral or summation is from -inf to +inf
	- Law of Large numbers
		- The average of large number of samples should be close to the expected value and will become closer to the expected value as more trials are performed
		- $\bar{X}_{n}=\frac{1}{n}\sum_{i=1}^{n}X_{i},\quad\bar{X}_{n}\xrightarrow{P}\mu\quad\text{(Weak Law)},\quad\text{and}\quad\bar{X}_{n}\xrightarrow{\text{a.s.}}\mu\quad\text{(Strong Law)}.$
	- Final formula
		- $D_{\text{KL}}(P_{\theta}\|Q_{\phi})\approx\frac{1}{n}\sum_{i=1}^{n}\log\frac{p_{\theta}(x_{i})}{q_{\phi}(x_{i})}$
	- Are both same? NO
		- The KL divergence from $Q$ to $P$ is defined as:
		- $D_{\text{KL}}(Q\|P)=\int q(x)\log\frac{q(x)}{p(x)}\,dx$
		- Forward KL is not equal to Backward KL
		- Forward KL - mean seeking behaviour
		- Backward KL - mode seeking behaviour
	- If you are using cross entropy -> you are essentially using Forward KL (atleast the component)
	- KL divergence is also called -> relative entropy
		-
		-
	-
- $D_{\text{KL}}(P_{\theta}\|Q_{\phi})=\int p_{\theta}(x)\log\frac{p_{\theta}(x)}{q_{\phi}(x)}\,dx$
-
-
-