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