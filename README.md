# Exploring diffusion model and its application to solve the downstream task
Here, we summarize our exploration of any diffusion model we experimented with. We experiment on RTX 3090. 

---

### Latent diffusion model (LDM) / stable diffusion [Github](https://github.com/CompVis/latent-diffusion)
**Summary**: LDM proposes an efficient diffusion model in latent space (smaller size than the original image) and cross-attention network to collaborate with the condition model.\
**Strength**: Able to generate images from given conditions such as depth, image, or text. The result is promising and trained with over a hundred million LAION datasets. \
**Problem**:  Does not work for scene text generation and image editing. The resulting image is typically unrealistic. 

---
