## **What are Markov Chains?**
Markov Chains are mathematical systems that undergo transitions from one state to another within a finite or countable state space, following a probabilistic rule. The key characteristic is that the future state depends only on the current state, not on the sequence of past states.

---
- watch {{video https://www.youtube.com/watch?v=i3AkTO9HLXo&list=PLM8wYQRetTxBkdvBtz-gw8b9lcVkdXQKV}}
-
- ## **Key Properties**
  1. **Markov Property**:
	- The probability of moving to the next state depends only on the current state.
	- Mathematically:  
	  \( P(X_{n+1} = x | X_n = x_n, X_{n-1} = x_{n-1}, ..., X_0 = x_0) = P(X_{n+1} = x | X_n = x_n) \)
	  
	  2. **State Space**:
	- The set of all possible states a system can occupy.
	  
	  3. **Transition Probability**:
	- Probability of moving from one state to another, often represented in a **transition matrix**.
	  
	  4. **Stationary Distribution**:
	- A probability distribution that remains unchanged as the chain progresses over time.
	  
	  5. **Irreducibility**:
	- A Markov chain is irreducible if it is possible to reach any state from any other state.
	  
	  6. **Periodicity**:
	- A state is periodic if the chain returns to that state at multiples of some fixed time step.
	  
	  7. **Ergodicity**:
	- A chain is ergodic if it is irreducible, aperiodic, and has a stationary distribution.
	  
	  ---
- ## **Types of Markov Chains**
  1. **Discrete-Time Markov Chains (DTMC)**:
	- Transitions occur at fixed time intervals.
	  2. **Continuous-Time Markov Chains (CTMC)**:
	- Transitions occur at continuous time intervals.
	  
	  ---
- ## **Applications**
  1. **Physics**: Modeling particle movement.
  2. **Economics**: Predicting market trends.
  3. **Computer Science**: PageRank algorithm in search engines.
  4. **Biology**: DNA sequence analysis.
  5. **Queueing Theory**: Modeling server systems.
  
  ---
- ## **Advantages**
- Simple to implement.
- Useful for modeling sequential processes.
- Foundational for advanced probabilistic models like Hidden Markov Models ( [[HMM]] s).
  
  ---
- ## **Limitations**
- Assumes the Markov property, which may not hold for all systems.
- State space size can grow exponentially, making computation difficult.
- Transition probabilities can be hard to estimate for complex systems.
-
- **Markov Chains in AI/ML**
	- **Overview**
		- Markov chains leverage the **Markov property** (memorylessness), where future states depend only on the current state.
		- Applications span NLP, Graph Analysis, Reinforcement Learning, Time Series, Computer Vision, Bioinformatics, and more.
	- **Subfields**
		- [[Natural Language Processing (NLP)]]
			- **Text Generation**
				- N-gram models predict the next word based on the previous \( n-1 \) words.
				- Hidden Markov Models (HMMs) for tasks like part-of-speech tagging, named entity recognition, and speech recognition.
			- **Language Modeling**
				- Early statistical language models relied on Markov assumptions for tasks like machine translation and auto-completion.
		- [[Graph Analysis]]
			- **PageRank**
				- Models web surfing as a Markov chain, where transitions between web pages are probabilistic.
			- **Random Walks**
				- Analyze graph structure (e.g., social networks, recommendation systems) by simulating transitions between nodes.
			- **Diffusion Processes**
				- Model information or influence spread in networks using Markovian dynamics.
		- [[Reinforcement Learning (RL)]]
			- **Markov Decision Processes (MDPs)**
				- Formally define RL environments, where agents choose actions based on the current state to maximize rewards.
			- **Partial Observability (POMDPs)**
				- Extend MDPs for partially observable states while retaining Markovian transitions.
			- **Model-Based RL**
				- Learn transition dynamics as Markov chains to simulate state transitions and plan optimal policies.
		- [[Time Series Analysis]]
			- **State Prediction**
				- Use HMMs to infer hidden states (e.g., market regimes, weather conditions) from observed data.
			- **Regime-Switching Models**
				- Capture economic or financial cycles (e.g., recession vs. growth) with Markovian transitions.
			- **Autoregressive Models**
				- Assume Markov properties for short-term dependencies (e.g., ARIMA).
		- [[Computer Vision]]
			- **Markov Random Fields (MRFs)**
				- Model spatial dependencies in images for tasks like denoising, segmentation, and stereo matching.
			- **MCMC Sampling**
				- Techniques like Gibbs sampling infer posterior distributions in MRFs.
		- [[Bioinformatics]]
			- **Sequence Analysis**
				- HMMs predict gene structures, protein folding, and align DNA/RNA sequences by modeling transitions between biological states.
		- [[Probabilistic Inference]]
			- **Markov Chain Monte Carlo (MCMC)**
				- Sample from complex distributions (e.g., Bayesian networks) using chains that converge to target distributions.
		- [[Recommendation Systems]]
			- **User Behavior Modeling**
				- Track transitions between user states (e.g., product views, clicks) to predict next actions and recommend items.
	- **Strengths and Limitations**
		- **Strengths**
			- Computationally efficient, analytically tractable, and foundational for sequential decision-making.
		- **Limitations**
			- The memoryless assumption may fail for long-range dependencies, leading to the use of deeper models (e.g., RNNs, Transformers).
	- **Summary**
		- Markov chains and their generalizations (HMMs, MDPs, MRFs) provide a versatile framework for modeling sequential, spatial, and state-dependent processes across AI/ML.
		- They enable efficient algorithms for prediction, inference, and optimization, even as more complex models address their limitations in capturing long-term dependencies.
	- **Markov Chains**
		- Used in [[N-Grams]] for text generation.
		- Applied in [[Viterbi Algorithm]] for POS tagging.