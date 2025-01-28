- In Part-of-Speech (POS) tagging, the goal is to assign the correct POS tag (e.g., noun, verb, adjective) to each word in a sentence. HMM provides a probabilistic framework for solving this by modeling the problem as finding the most probable sequence of hidden states (POS tags) given the observed sequence (words in the sentence).
  
  ---
- ## HMM Components
  
  1. **States**: The POS tags (e.g., Noun, Verb, Adjective). These are the *hidden states*.  
  2. **Observations**: The words in the sentence (e.g., "The cat runs"). These are the *observable outputs*.  
  3. **Transition probabilities (\( P(t_i | t_{i-1}) \))**: The probability of transitioning from one POS tag to another.  
   Example: \( P(\text{Verb | Noun}) \).  
  4. **Emission probabilities (\( P(w_i | t_i) \))**: The probability of a word being emitted by a particular POS tag.  
   Example: \( P(\text{"cat" | Noun}) \).  
  5. **Initial probabilities (\( P(t_1) \))**: The probability of a POS tag being the start of a sequence.  
   Example: \( P(\text{Noun}) \).
  
  ---
- ## Problem Statement
  
  Given a sequence of words \( w_1, w_2, \dots, w_n \), find the most likely sequence of POS tags \( t_1, t_2, \dots, t_n \).
  
  This involves maximizing the joint probability:
  \[
  P(t_1, t_2, \dots, t_n | w_1, w_2, \dots, w_n)
  \]
  Using Bayes' Theorem:
  \[
  P(t_1, t_2, \dots, t_n | w_1, w_2, \dots, w_n) \propto P(w_1, w_2, \dots, w_n | t_1, t_2, \dots, t_n) \cdot P(t_1, t_2, \dots, t_n)
  \]
  
  ---
- ## Decomposing the Probability
  
  1. **Emission Probability** (\( P(w_1, w_2, \dots, w_n | t_1, t_2, \dots, t_n) \)):  
   Assumes that each word depends only on its corresponding tag:  
   \[
   P(w_1, w_2, \dots, w_n | t_1, t_2, \dots, t_n) = \prod_{i=1}^n P(w_i | t_i)
   \]
  
  2. **Transition Probability** (\( P(t_1, t_2, \dots, t_n) \)):  
   Assumes a first-order Markov property, where each tag depends only on the previous tag:  
   \[
   P(t_1, t_2, \dots, t_n) = P(t_1) \prod_{i=2}^n P(t_i | t_{i-1})
   \]
  
  ---
- ## Objective: Find the Most Likely Sequence
  
  We need to maximize:
  \[
  P(t_1, t_2, \dots, t_n | w_1, w_2, \dots, w_n) \propto \prod_{i=1}^n P(w_i | t_i) \cdot \prod_{i=2}^n P(t_i | t_{i-1}) \cdot P(t_1)
  \]
  
  ---
- ## Using the Viterbi Algorithm
  
  To efficiently compute the most likely sequence of tags, we use the **Viterbi Algorithm**, which avoids enumerating all possible sequences:
  
  1. **Initialization**:  
   For each tag \( t \):  
   \[
   V_1(t) = P(t) \cdot P(w_1 | t)
   \]
  
  2. **Recursion**:  
   For each word \( i \) (2 to \( n \)) and each tag \( t \):  
   \[
   V_i(t) = \max_{t'} [V_{i-1}(t') \cdot P(t | t') \cdot P(w_i | t)]
   \]
  
  3. **Termination**:  
   Find the maximum probability for the last word:  
   \[
   \max_t V_n(t)
   \]
  
  4. **Backtracking**:  
   Trace back through the tags to find the sequence.
  
  ---
- ## Example
  
  Consider the sentence: **"The cat runs"**
- **Words**: [The, cat, runs]
- **Tags**: [Det, Noun, Verb]
  
  Given the transition and emission probabilities, the Viterbi algorithm computes the most likely sequence of tags.
  
  This mathematical formulation makes HMM a robust tool for POS tagging in NLP.