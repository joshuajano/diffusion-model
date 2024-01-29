# Exploring diffusion model and its application to solve the downstream task
Here, we summarize our exploration of any diffusion model we experimented with. We experiment on RTX 3090. 

---

### High-Resolution Image Synthesis with Latent Diffusion Models (LDM) / stable diffusion, CVPR 2022 [Github](https://github.com/CompVis/latent-diffusion)
**Summary**: LDM proposes an efficient diffusion model in latent space (smaller size than the original image) and cross-attention network to collaborate with the condition model.\
**Strength**: Able to generate images from given conditions such as depth, image, or text. The result is promising and trained with over a hundred million data on LAION datasets. \
**Weakness**:  Does not work for scene text generation and image editing. The resulting image is typically unrealistic. 

### DiffusionCLIP: Text-Guided Diffusion Models for Robust Image Manipulation, CVPR 2022 [Github](https://github.com/gwang-kim/DiffusionCLIP)
**Summary**: This paper presents image editing with a diffusion model from the given prompt. They proposed forward DDIM (where the noisy image can be obtained by adding the predicted noise) and CLIP loss for editing the image.\
**Strength**: The resulting image has a consistent structure with a different style than the original image. \
**Weakness**: The key idea is keeping the gradient from each denoising step, which requires a huge GPU memory. In our case, the maximum step is 6. 

### Blended Diffusion for Text-driven Editing of Natural Images, CVPR 2022 [Github](https://github.com/omriav/blended-diffusion)
**Summary**: This paper presents localization image editing with a diffusion model from the given prompt and mask. They introduce masked CLIP loss to edit the image while maintaining the original image.\
**Strength**: The resulting image has a consistent structure with the original image, while the target region is changed with the given prompt. \
**Weakness**: This is per-scene optimization and requires more than 30 minutes.  

### RePaint: Inpainting using Denoising Diffusion Probabilistic Models, CVPR 2022 [Github](https://github.com/andreas128/RePaint)
**Summary**: This paper presents image inpainting with a diffusion model from the given region.\
**Strength**: The resulting image is consistent with the original image, while the inpainted region has a similar structure to the original image. \
**Weakness**: This is per-scene optimization and requires more than 45 minutes.  

### MagicMix: Semantic Mixing with Diffusion Models, ArXiv 2022 [Github](https://magicmix.github.io/)
**Summary**: This paper presents semantic blending that mixes two different concepts in a semantic manner to synthesize a novel concept while preserving the spatial layout and geometry. The key to maintaining the spatial layout is injecting forwarded noisy images during denoising. \
**Strength**: The resulting image has the original input's spatial and geometry information, but the content changes following the given text. \
**Weakness**: No code available. Also, we need to properly select the injection step. If not, the result produces a ghosting effect or changes the spatial layout.

### Imagic: Text-Based Real Image Editing with Diffusion Models, CVPR 2023 [Github](https://imagic-editing.github.io/)
**Summary**: This paper presents text-based image editing with a diffusion model by introducing a sampling interpolation step. \
**Strength**: The posture and composition of the resulting image are changed while preserving its original characteristics. \
**Weakness**: This is per-scene optimization and takes around 8 minutes per scene. Second, we need to properly set the scale of the interpolation value. 

### Prompt-to-Prompt Image Editing with Cross-Attention Control, ICLR 2023 [Github](https://prompt-to-prompt.github.io/)
**Summary**: This paper presents text-based image editing with a diffusion model by controlling only the cross-attention value.  \
**Strength**: There is no optimization. The posture and composition of the resulting image are changed while preserving its original characteristics. \
**Weakness**: We need to properly set the value for the cross-attention. The success of the editing process heavily relies on the condition model. 

### Null-text Inversion for Editing Real Images using Guided Diffusion Models, CVPR 2023 [Github](https://null-text-inversion.github.io/)
**Summary**: Given the RGB image, this paper presents text-based image editing with a diffusion model by controlling only the cross-attention value. \
**Strength**: The posture and composition of the resulting image are changed while preserving its original characteristics. \
**Weakness**: Per-scene optimization. We need to properly set the value for the cross-attention. The success of the editing process heavily relies on the condition model. 




