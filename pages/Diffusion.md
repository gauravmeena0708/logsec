- Diffusion models are a class of generative models that create data by learning to reverse a noise-adding process. They start with random noise and iteratively refine it to generate samples that resemble the training data.
	- **Forward Process**: Gradually adds Gaussian noise to the data, destroying its structure over several steps.
	- **Reverse Process**: Learns to denoise iteratively, reconstructing the data from noise.
- Betterment over VAE
	- VAE gives blurry outputs