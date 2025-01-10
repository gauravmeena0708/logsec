- Naive Bayes formula -> $P(C\vert X)=\frac{P\left(X\right)P(X\vert C)}{P\left(C\right)}$
- For unigram $P(C|X)=\frac{P(C)\prod_{i=1}^{n}P(w_{i}|C)}{P(X)}$
- Using MLE $P(w_{i}|C)=\frac{\text{count}(w_{i},C)}{\text{count}(C)}$
- ## Maximum Likelihood Estimation for Unigrams and Bigrams
  
  For **unigrams**, the MLE formula for the probability of a word \( w_i \) in a class \( C \) is:
  
  $$
  P(w_i | C) = \frac{\text{count}(w_i, C)}{\text{count}(C)}
  $$
  
  For the sentence "I am going to eat", we have:
- Total number of words in the sentence \( \text{count}(C) = 4 \).
- The MLE probability for each word is:
  
  $$
  P(\text{I} | C) = \frac{1}{4}, \quad P(\text{am} | C) = \frac{1}{4}, \quad P(\text{going} | C) = \frac{1}{4}, \quad P(\text{to} | C) = \frac{1}{4}, \quad P(\text{eat} | C) = \frac{1}{4}
  $$
  
  For **bigrams**, the MLE formula for the probability of a bigram \( (w_i, w_{i+1}) \) in class \( C \) is:
  
  $$
  P(w_i, w_{i+1} | C) = \frac{\text{count}(w_i, w_{i+1}, C)}{\text{count}(w_i, C)}
  $$
  
  For the sentence "I am going to eat", the bigrams are:
- \( (\text{I}, \text{am}) \)
- \( (\text{am}, \text{going}) \)
- \( (\text{going}, \text{to}) \)
- \( (\text{to}, \text{eat}) \)
  
  Each bigram appears once, so the MLE probabilities for each bigram are:
  
  $$
  P(\text{I}, \text{am} | C) = \frac{1}{1} = 1, \quad P(\text{am}, \text{going} | C) = \frac{1}{1} = 1, \quad P(\text{going}, \text{to} | C) = \frac{1}{1} = 1, \quad P(\text{to}, \text{eat} | C) = \frac{1}{1} = 1
  $$