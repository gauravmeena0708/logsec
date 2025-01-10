## Levenshtein Distance

Levenshtein Distance, also known as **edit distance**, is a metric used to measure the difference between two sequences (usually strings). It counts the minimum number of single-character edits (insertions, deletions, or substitutions) required to transform one string into the other.

For example:
- The Levenshtein distance between "kitten" and "sitting" is 3:
	- kitten → sitten (substitution of k → s)
	- sitten → sittin (substitution of e → i)
	- sittin → sitting (insertion of g)
- ### Operations in Levenshtein Distance
  There are three allowed operations:
- **Insertion**: Insert a character into the string.
- **Deletion**: Delete a character from the string.
- **Substitution**: Replace one character with another.
	- ### Formula
		- Given two strings, `s1` of length `n` and `s2` of length `m`, the Levenshtein distance is defined by the following recursive relation:
	-
	-