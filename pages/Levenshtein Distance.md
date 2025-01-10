## Levenshtein Distance
	- Levenshtein Distance, also known as **edit distance**, is a metric used to measure the difference between two sequences (usually strings). It counts the minimum number of single-character edits (insertions, deletions, or substitutions) required to transform one string into the other.
	- For example: The Levenshtein distance between "kitten" and "sitting" is 3:
		- kitten → sitten (substitution of k → s)
		- sitten → sittin (substitution of e → i)
		- sittin → sitting (insertion of g)
- ### Operations in Levenshtein Distance
	- There are three allowed operations:
	- **Insertion**: Insert a character into the string.
	- **Deletion**: Delete a character from the string.
	- **Substitution**: Replace one character with another.
- ### Formula
	- Given two strings, `s1` of length `n` and `s2` of length `m`, the Levenshtein distance is defined by the following recursive relation:
	- D[i, j] =
	  if i = 0 then j
	  else if j = 0 then i
	  else
	  min(
	  D[i-1, j] + 1, // Deletion
	  D[i, j-1] + 1, // Insertion
	  D[i-1, j-1] + cost // Substitution (if s1[i-1] ≠ s2[j-1])
	  )
-
	- Where:
	- `D[i, j]` is the distance between the first `i` characters of `s1` and the first `j` characters of `s2`.
	- The `cost` is `0` if the characters are the same, and `1` if they are different.
	  
	  ---
	- ### Levenshtein Distance Algorithm
		- The following is a step-by-step explanation of the **dynamic programming** algorithm used to calculate the Levenshtein distance:
		- 1. **Initialize a matrix**:
			- Create a matrix `D` where the entry `D[i, j]` holds the Levenshtein distance between the first `i` characters of `s1` and the first `j` characters of `s2`. The dimensions of the matrix will be `(n + 1) x (m + 1)`, where `n` and `m` are the lengths of `s1` and `s2`, respectively.
		- 2. **Base cases**:
			- For the first row (`i = 0`), the distance is the number of insertions required to transform an empty string into the first `j` characters of `s2`, so `D[0, j] = j`.
			- For the first column (`j = 0`), the distance is the number of deletions required to transform the first `i` characters of `s1` into an empty string, so `D[i, 0] = i`.
		- 3. **Fill the matrix**:
			- For each pair of indices `(i, j)`, compute the minimum of the following three options:
			- **Deletion**: `D[i-1, j] + 1`
			- **Insertion**: `D[i, j-1] + 1`
			- **Substitution**: `D[i-1, j-1] + cost`, where `cost` is `0` if the characters are the same, and `1` if they are different.
		- 4. **Final answer**:
			- After filling the matrix, the value in `D[n, m]` will contain the Levenshtein distance between the two strings.
	- ### Pseudocode
	  
	  ``python
	  def levenshtein_distance(s1, s2):
	    n = len(s1)
	    m = len(s2)``
	-
	- # Create a matrix to store the distances
	    D = [[0] * (m + 1) for _ in range(n + 1)]
	- # Initialize base cases
	- ``for i in range(n + 1):
	        D[i][0] = i
	    for j in range(m + 1):
	        D[0][j] = j``
	- # Fill the matrix
	    for i in range(1, n + 1):
	        for j in range(1, m + 1):
	            cost = 0 if s1[i - 1] == s2[j - 1] else 1
	            D[i][j] = min(
	                D[i - 1][j] + 1,   # Deletion
	                D[i][j - 1] + 1,   # Insertion
	                D[i - 1][j - 1] + cost  # Substitution
	            )
	- # Return the Levenshtein distance
	    return D[n][m]
	-