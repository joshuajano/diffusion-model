# Exploring diffusion model and its application to solve the downstream task
Here, we summarize our exploration of any diffusion model we experimented with. We experiment on RTX 3090. 

---

### High-Resolution Image Synthesis with Latent Diffusion Models (LDM) / stable diffusion, CVPR 2022 [Github](https://github.com/CompVis/latent-diffusion)
**Summary**: LDM proposes an efficient diffusion model in latent space (smaller size than the original image) and cross-attention network to collaborate with the condition model.\
**Strength**: Able to generate images from given conditions such as depth, image, or text. The result is promising and trained with over a hundred million data on LAION datasets. \
**Problem**:  Does not work for scene text generation and image editing. The resulting image is typically unrealistic. 

---

### DiffusionCLIP: Text-Guided Diffusion Models for Robust Image Manipulation, CVPR 2022 [Github](https://github.com/gwang-kim/DiffusionCLIP)
**Summary**: This paper presents image editing with a diffusion model from the given prompt. They proposed forward DDIM (where the noisy image can be obtained by adding the predicted noise) and CLIP loss for editing the image.
