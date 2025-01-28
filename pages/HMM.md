- Hidden Markov models are derived from [[Markov chains]]. HMM are used when we don't have direct access to the variable that needs to be predicted but we have access to [[Latent Space]] or a variable that depends on the variable that needs to be predited.
	- ### 1. Weather Prediction
		- Imagine you are trying to guess the weather (Sunny, Rainy, or Cloudy) over the next few days. You don't have direct access to the weather data, but you observe your friend’s clothing choices each day:
		- **Hidden states**: The actual weather (Sunny, Rainy, or Cloudy) — which you can’t directly see.
		- **Observed states**: Your friend’s clothing (e.g., T-shirt, Raincoat, Jacket).
		  
		  For example:
			- On Sunny days, your friend mostly wears T-shirts.
			- On Rainy days, your friend wears a Raincoat.
			- On Cloudy days, they often wear a Jacket.
		- Using the patterns of what your friend wears, you can make a good guess about the hidden weather conditions over a period of time.
	- ### 2. Recognizing Mood Through Music
		- Imagine you are trying to figure out your friend Laddu's mood based on the type of music they are listening to:
		- **Hidden states**: Laddu’s mood (Happy, Sad, or Energetic) — which is not directly visible.
		- **Observed states**: The type of music Laddu plays (Pop, Ballads, Rock).
		  
		  For example:
			- When Laddu is happy, they often listen to Pop music.
			- When Laddu feels sad, they listen to Ballads.
			- When Laddu is energetic, they play Rock music.
		- Even though you can't see Laddu's mood directly, by observing their music choices over time, you can make an educated guess about their hidden mood.
- ## Applications
	- [[POS Tagging]] in [[ELL884 NLP]]