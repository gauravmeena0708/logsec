- 3 popular methods
	- [[VAE]]
	- [[GAN]]
	- [[Diffusion]]
- ## Comparision
	- | **Aspect**               | **Variational Autoencoders (VAE)**                                   | **Generative Adversarial Networks (GAN)**                    | **Diffusion Models**                                      |
	  |--------------------------|---------------------------------------------------------------------|--------------------------------------------------------------|----------------------------------------------------------|
	  | **Purpose**              | Probabilistic generation and representation learning.              | Adversarially trained to generate realistic data.            | Generative modeling via iterative noise reduction.       |
	  | **Training Objective**   | Minimize the Evidence Lower Bound (ELBO): reconstruction + KL divergence. | Minimize adversarial loss between generator and discriminator.| Minimize noise prediction or reverse process error.      |
	  | **Architecture**         | Encoder-decoder with latent variable sampling.                    | Generator-discriminator framework.                          | Forward and reverse processes modeling noise transitions.|
	  | **Strengths**            | - Good latent space representation. <br> - Easy to condition outputs. | - High-quality, realistic outputs. - Wide range of applications.| - Stable training. <br> - Handles multi-modal distributions well.|
	  | **Weaknesses**           | - Blurry outputs. <br> - Difficulty capturing fine details.       | - Training instability. <br> - Mode collapse issues.         | - Computationally expensive. <br> - Requires large datasets. |
	  | **Applications**         | - Data compression. <br> - Anomaly detection. <br> - Semi-supervised learning. | - Image synthesis. <br> - Style transfer. <br> - Super-resolution. | - Image denoising. <br> - Text-to-image generation.      |
	  | **Key Components**       | - KL divergence for regularization. <br> - Reparameterization trick. | - Generator to create data. <br> - Discriminator to differentiate real and fake data. | - Noise scheduler. <br> - U-Net or transformer-based denoising network. |
	  | **Output Quality**       | Often blurry due to focus on likelihoods.                         | High quality but prone to artifacts.                        | High quality, often more diverse and detailed.           |
	  | **Training Complexity**  | Moderate.                                                        | High, due to adversarial dynamics.                          | Very high, due to iterative denoising.                   |
	  | **State of the Art Uses**| Representation learning in latent space.                          | Realistic image and video generation.                       | Advanced generative tasks (e.g., text-to-image with DALL·E, Stable Diffusion). |