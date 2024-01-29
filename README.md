# Exploring diffusion model and its application to solve the downstream task
Here, we summarize our exploration of any diffusion model we experimented with. We experiment on RTX 3090. 

---

### Latent diffusion model (LDM) / stable diffusion [Github](https://github.com/CompVis/latent-diffusion)
**Summary**: LDM proposes an efficient diffusion model in latent space (smaller size than the original image) and cross-attention network to collaborate with the condition model.

**Problem**:  Does not work for scene text generation and image editing. 
