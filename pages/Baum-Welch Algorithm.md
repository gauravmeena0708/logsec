- Baum-Welch Algorithm is used in POS Tagging in Natural Language Processing. It assumes the words of the sentences as latent variables and Noun/verb/Adjectives as Hidden Variables of [[HMM]] model.
- # Mathematics of the Baum-Welch Algorithm
  
  The **Baum-Welch algorithm**, an Expectation-Maximization (EM) algorithm, is used to estimate the parameters of a Hidden Markov Model (HMM). It iteratively maximizes the likelihood of observed data by refining:
  
  1. **Initial probabilities (\( \pi \))**
  2. **Transition probabilities (\( a_{ij} \))**
  3. **Emission probabilities (\( b_j(o_k) \))**
  
  ---
- ## Key Notations
- \( N \): Number of states in the HMM.
- \( M \): Number of possible observations.
- \( T \): Length of the observation sequence.
- \( O = \{o_1, o_2, \dots, o_T\} \): Observation sequence.
- \( \pi = \{\pi_i\} \): Initial probabilities (\( \pi_i = P(q_1 = i) \)).
- \( A = \{a_{ij}\} \): Transition probabilities (\( a_{ij} = P(q_{t+1} = j | q_t = i) \)).
- \( B = \{b_j(o_t)\} \): Emission probabilities (\( b_j(o_t) = P(o_t | q_t = j) \)).
- \( \alpha_t(i) \): Forward probability, the probability of observing \( o_1, o_2, \dots, o_t \) and being in state \( i \) at time \( t \).
- \( \beta_t(i) \): Backward probability, the probability of observing \( o_{t+1}, o_{t+2}, \dots, o_T \) given the state at time \( t \) is \( i \).
- \( \gamma_t(i) \): Probability of being in state \( i \) at time \( t \), given the observation sequence \( O \).
- \( \xi_t(i, j) \): Probability of transitioning from state \( i \) to state \( j \) at time \( t \), given \( O \).
  
  ---
- ## Objective
  
  We want to maximize the likelihood of the observation sequence \( P(O | \pi, A, B) \) by iteratively refining \( \pi, A, B \).
  
  ---
- ## E-Step: Compute Responsibilities
  
  1. **Forward Probabilities (\( \alpha_t(i) \)):**
  
   \[
   \alpha_1(i) = \pi_i \cdot b_i(o_1)
   \]
   \[
   \alpha_{t+1}(j) = \sum_{i=1}^N \alpha_t(i) \cdot a_{ij} \cdot b_j(o_{t+1})
   \]
  
  2. **Backward Probabilities (\( \beta_t(i) \)):**
  
   \[
   \beta_T(i) = 1
   \]
   \[
   \beta_t(i) = \sum_{j=1}^N a_{ij} \cdot b_j(o_{t+1}) \cdot \beta_{t+1}(j)
   \]
  
  3. **State Probability (\( \gamma_t(i) \)):**
  
   The probability of being in state \( i \) at time \( t \), given the observation sequence:
   \[
   \gamma_t(i) = \frac{\alpha_t(i) \cdot \beta_t(i)}{\sum_{k=1}^N \alpha_t(k) \cdot \beta_t(k)}
   \]
  
  4. **Transition Probability (\( \xi_t(i, j) \)):**
  
   The probability of transitioning from state \( i \) to state \( j \) at time \( t \), given \( O \):
   \[
   \xi_t(i, j) = \frac{\alpha_t(i) \cdot a_{ij} \cdot b_j(o_{t+1}) \cdot \beta_{t+1}(j)}{\sum_{p=1}^N \sum_{q=1}^N \alpha_t(p) \cdot a_{pq} \cdot b_q(o_{t+1}) \cdot \beta_{t+1}(q)}
   \]
  
  ---
- ## M-Step: Update Model Parameters
  
  1. **Update Initial Probabilities (\( \pi \)):**
  
   \[
   \pi_i = \gamma_1(i)
   \]
  
  2. **Update Transition Probabilities (\( A \)):**
  
   \[
   a_{ij} = \frac{\sum_{t=1}^{T-1} \xi_t(i, j)}{\sum_{t=1}^{T-1} \gamma_t(i)}
   \]
  
  3. **Update Emission Probabilities (\( B \)):**
  
   For each observation \( k \):
   \[
   b_j(o_k) = \frac{\sum_{t=1}^T \gamma_t(j) \cdot \mathbb{1}(o_t = o_k)}{\sum_{t=1}^T \gamma_t(j)}
   \]
   Here, \( \mathbb{1}(o_t = o_k) \) is 1 if \( o_t \) is equal to \( o_k \), otherwise 0.
  
  ---
- ## Iterative Process
  
  1. Initialize \( \pi, A, B \) randomly or based on prior knowledge.
  2. Perform the **E-step** to compute \( \gamma_t(i) \) and \( \xi_t(i, j) \) using the forward and backward probabilities.
  3. Perform the **M-step** to update \( \pi, A, B \).
  4. Repeat steps 2–3 until convergence (e.g., when the change in likelihood \( P(O | \pi, A, B) \) is below a threshold).
  
  ---
- ## Likelihood of the Observation Sequence
  
  The likelihood of the observation sequence is calculated as:
  \[
  P(O | \pi, A, B) = \sum_{i=1}^N \alpha_T(i)
  \]
  This is used to monitor convergence.
  
  ---
- ## Summary
  
  The Baum-Welch algorithm alternates between the **E-step** (responsibility calculation) and the **M-step** (parameter updates) to iteratively improve the HMM parameters. It ensures the likelihood of the observed sequences increases at each iteration, converging to a local maximum.