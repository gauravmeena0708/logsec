# Data Mining Notes: Apriori Principle, Association Rule Mining, and Frequent Itemset Mining
- ## 1. Apriori Principle
- ### Definition
  The **Apriori Principle** states:
- If an itemset is **frequent**, then all of its subsets must also be frequent.
- Conversely, if an itemset is **infrequent**, all of its supersets will also be infrequent.
- ### Key Points:
- **Support**: The proportion of transactions in which the itemset appears.
  \[
  \text{Support} = \frac{\text{Number of Transactions Containing Itemset}}{\text{Total Transactions}}
  \]
- The Apriori Principle helps in **pruning** the search space by eliminating candidate itemsets that cannot be frequent.
- ### Example:
- If `{A, B}` is infrequent, then `{A, B, C}` and `{A, B, D}` cannot be frequent.
  
  ---
- ## 2. Association Rule Mining
- ### Definition
  Association Rule Mining identifies **relationships** between items in a transaction database.
- ### Rule Format:
- **Rule**: \( X \rightarrow Y \)
	- \( X \): Antecedent (if this happens...)
	- \( Y \): Consequent (...then that happens).
- ### Metrics:
  1. **Support**: 
   \[
   \text{Support}(X \rightarrow Y) = \frac{\text{Transactions Containing Both } X \text{ and } Y}{\text{Total Transactions}}
   \]
  2. **Confidence**: 
   \[
   \text{Confidence}(X \rightarrow Y) = \frac{\text{Support}(X \cup Y)}{\text{Support}(X)}
   \]
	- Measures the likelihood of \( Y \) given \( X \).
	  3. **Lift**: 
	  \[
	  \text{Lift}(X \rightarrow Y) = \frac{\text{Confidence}(X \rightarrow Y)}{\text{Support}(Y)}
	  \]
	- Measures how much more likely \( Y \) is given \( X \) compared to random chance.
- ### Example:
- Rule: \{Milk\} → \{Bread\}
	- Support: 30%
	- Confidence: 70%
	- Lift: 1.2
	  
	  ---
- ## 3. Frequent Itemset Mining
- ### Definition
  Frequent Itemset Mining aims to find itemsets that occur frequently in a dataset, based on a minimum support threshold.
- ### Steps:
  1. **Candidate Generation**: Generate all possible itemsets of length \( k \).
  2. **Pruning**: Use the Apriori Principle to eliminate infrequent candidates.
  3. **Counting Support**: Calculate support for remaining candidates.
  4. **Repeat**: Increase \( k \) and repeat until no more frequent itemsets can be found.
- ### Algorithms:
- **Apriori Algorithm**: Uses the Apriori Principle for efficient frequent itemset mining.
- **FP-Growth**: Builds a compact **Frequent Pattern Tree** for mining without candidate generation.
- ### Example:
  **Dataset**:
  | Transaction ID | Items           |
  |----------------|------------------|
  | T1             | Milk, Bread, Butter |
  | T2             | Milk, Bread       |
  | T3             | Bread, Butter     |
  | T4             | Milk, Butter      |
  
  **Frequent Itemsets (Min Support = 50%)**:
- 1-itemsets: \{Milk\}, \{Bread\}, \{Butter\}
- 2-itemsets: \{Milk, Bread\}, \{Bread, Butter\}
- 3-itemsets: \{Milk, Bread, Butter\}
  
  ---
- ## Summary
- **Apriori Principle** helps reduce computational effort in frequent itemset mining.
- **Association Rule Mining** uncovers hidden relationships using rules.
- **Frequent Itemset Mining** identifies the most common itemsets for generating rules.
  
  ---