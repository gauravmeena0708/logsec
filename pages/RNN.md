- {{video https://www.youtube.com/watch?v=4KpRP-YUw6c}}
	- Recurrent NN
	- Applications - sequential data
		- Sentence
		- Time series
		- Speech
	- Problem: Text classification of sentences
		- {{youtube-timestamp 523}}
		- How to give input to NN? -> Vectorize
			- One-hot
			- Bag of words
			- Tf-IDF
		- Problem
			- One vector for each word
			- pass vector of each word of sentence as input
			- if vector size is 12, 4 word sentence will have input size of 48 and 5 word sentence will have input of 60.
			- lets say vocab is of 10000 words -> 5 word sentence would have 950000 as zero padding if max sentence has 100 as length
			- Issues: variable length, sequence information, zero padding leads to unnecessary computation, issues in prediction
		- Uses in NLP:
			- Sentiment analysis
			- Sentence completion
			- Translation
- {{video https://www.youtube.com/watch?v=BjWqCcbusMM}}
	- Problem
		- Variable length
		- Sequence matters
	- RNN is similar to ANN with 2 big diff
		- whole input doesn't go at a time -> input goes sequentially
		- RNN's are not feed forward -> concept of state -> gives feedback