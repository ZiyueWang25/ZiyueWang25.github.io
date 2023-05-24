---
layout: page
permalink: /TIL/
title: TIL
description: Today I learnt. Update daily.
nav: true
nav_order: 5
---
# 2023-05-20 - 2023-05-23

1. Virtual Try-on models:
	1. [TryOnDiffusion: A Tale of Two UNets](https://openaccess.thecvf.com/content/CVPR2023/papers/Zhu_TryOnDiffusion_A_Tale_of_Two_UNets_CVPR_2023_paper.pdf): parallel-UNet, cross-attention, cascade diffusion, FiLM, Efficient UNet. Amazing results!
	2. [High-Resolution Virtual Try-On with Misalignment and Occlusion-Handled Conditions](https://arxiv.org/abs/2206.14180): classic Virtual Try On (VITON) model by warping the cloth first and then blend with the target person.
	3. [TryOnGAN](https://tryongan.github.io/tryongan/)
	4. [Single Stage Virtual Try-on via Deformable Attention Flows](https://arxiv.org/abs/2207.09161)
2. [FiLM](https://distill.pub/2018/feature-wise-transformations/): a way to combine concatenation & multiplication feature transformation.
3. Diffusion Model Related read:
	1. [What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/) by Lilian Weng
	2. [The Annotated Diffusion Model](https://huggingface.co/blog/annotated-diffusion) by huggingface
	3. [Diffusion Models: A Comprehensive Survey of Methods and Applications](https://arxiv.org/abs/2209.00796)
	4. [Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239): classic DDPM algorithm
	5. [Improved Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2102.09672): learning variance of the reverse diffusion process.
	6. [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502): DDIM , a more efficient iterative process for the reverse diffusion part.
	7. [Diffusion Models Beat GANs on Image Synthesis](https://arxiv.org/abs/2105.05233): classifier guidance
	8. [Classifier-Free Diffusion Guidance](https://arxiv.org/abs/2104.07636): classifier-free guidance
	9. [High-Resolution Image Synthesis with Latent Diffusion Models](https://ieeexplore.ieee.org/document/9878449): cross attention.
	10. [Image Super-Resolution via Iterative Refinement](https://arxiv.org/abs/2104.07636)
	11. [Cascaded Diffusion Models for High Fidelity Image Generation](https://arxiv.org/abs/2106.15282)
	12. [Palette: Image-to-Image Diffusion Models](https://arxiv.org/abs/2111.05826): image to image diffusion model
	13. [Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding](https://arxiv.org/abs/2205.11487): text-to-image model by leveraging LLM.
4. Human pose and segmentation:
	1. [Towards Accurate Multi-person Pose Estimation in the Wild](https://arxiv.org/abs/1701.01779)
	2. [Graphonomy: Universal Human Parsing via Graph Transfer Learning](https://arxiv.org/abs/1904.04536)
5. [Parti](https://sites.research.google/parti/): Pathways Autoregressive Text-to-Image model 


# 2023-05-17 - 2023-05-19

1. Replicating [Attention is all you need](https://arxiv.org/abs/1706.03762) paper in JAX/Flax/Optax.
# 2023-05-16
1. [How to pursue a career in technical AI alignment](https://forum.effectivealtruism.org/posts/7WXPkpqKGKewAymJf/how-to-pursue-a-career-in-technical-ai-alignment): this is amazing post about ML/DL/AI alignment.
# 2023-05-15
1. [Leverage Dopamine to Overcome Procrastination & Optimize Effort](https://hubermanlab.com/leverage-dopamine-to-overcome-procrastination-and-optimize-effort/): this podcast episode is interesting and informative. The biggest takeaway for me is to understand how our motivation level changes according to dopamine and what the dopamine circuit is like. It is also surprising to learn that we can leverage something that sucks to overcome procrastination. A good summary can be found [here](https://podcastnotes.org/huberman-lab/leverage-dopamine-to-overcome-procrastination-optimize-effort-huberman-lab/)
2. Instead of reading paper, I should spend more time getting my hands dirty. It is harder and has more direct impact on my career.

# 2023-05-14
1. [NeRF - Representing Scenes as Neural Radiance Fields for View Synthesis](https://www.matthewtancik.com/nerf): First time tackling 3D image synthesis problem. Followed [tiny_nerf.ipynb](https://github.com/bmild/nerf/blob/master/tiny_nerf.ipynb) notebook and added hierarchical sampling on it. [tiny_nerf_with_hierarchical_sampling.ipynb](https://colab.research.google.com/drive/1U18TrmcnL1TpZj1R-qv43hsxfu_DizOc?usp=sharing)
2. [NeRF in the Wild](https://nerf-w.github.io/): add a series of extensions to NeRF to address dynamic subjects captured under uncontrolled setting.
3. 

# 2023-05-13
1. [Project Starline](https://blog.google/technology/research/project-starline/): 3D display to connect people. [video](https://www.youtube.com/watch?v=kDgToq5aXh0&ab_channel=GoogleAR%26VR)
2. [Novel View Synthesis with Diffusion Models](https://3d-diffusion.github.io/): 3D generation from a few image pairs.
3. [NeRF in the Dark: High Dynamic Range View Synthesis from Noisy Raw Images](https://bmild.github.io/rawnerf/): 
4. [Time-Travel Rephotography](https://time-travel-rephotography.github.io/): use styleGAM2 framework to project old photo into modern high-resolution photos
5. [HyperNeRF: A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields](https://hypernerf.github.io/)

# 2023-05-12
1. [Whisper](https://openai.com/research/whisper): English speech recognition
2. [Zero Redundancy Optimizer](https://www.deepspeed.ai/tutorials/zero/) :partitioning various model training states across the available devices
3. [BLOOM: A 176B-Parameter Open-Access Multilingual Language Model](https://bigscience.huggingface.co/blog/bloom)
4. I got a personal poem written by Melanie Reed when we walk around Green Lake. It is beautiful and touching.

# 2023-05-11
1. [80,000 hours](https://80000hours.org/): 80,000 hours in your career. The [key ideas](https://80000hours.org/key-ideas/) page is amazing.
2. [PaLM2](https://blog.google/technology/ai/google-palm-2-ai-large-language-model/)
3. [UL2](https://ai.googleblog.com/2022/10/ul2-20b-open-source-unified-language.html): A way to include encoder like and decoder like training objective together.
4. Some exploration about green card application @ Australia, Germany, Netherlands and Sweden. Be mentally prepared for the Chinese discrimination in the USA.

# 2023-05-10 
1. [Why did all of the public reproduction of GPT-3 fail? In which tasks should we use GPT-3.5/ChatGPT?](https://jingfengyang.github.io/gpt): A practical point of view to compare different LLM reproduction and application issue.
2. [ImageBind](https://imagebind.metademolab.com/): wow, the idea is pretty straightforward: learning the joint embedding from multiple modalities. Using image as the central embedding. Interesting!

# 2023-05-09
1. [Harnessing the power of LLMs in Practice](https://github.com/Mooler0410/LLMsPracticalGuide): the chart inside is quite informative and the future trend is also thoughtful: evaluation on real-world datasets, alignment, safety.
2. To do great things, focus on small stuff. 
3. To make a fortune, help 1-billion people or make a grand breakthrough.


# 2023-05-08
1. [Now Page](https://nownownow.com/): A simple but quite informative and fun page created by Derek Sivers. 
2. [DataComp](https://www.datacomp.ai/): A framework about improving dataset by fixing model.
   1. [Detoxify](https://github.com/unitaryai/detoxify): model to remove unsafe content.
   2. Deduplication using constrastive learning. [link](https://arxiv.org/pdf/2112.04323.pdf)
   3. Face detection and blurring for privacy. [detection model](https://arxiv.org/abs/2105.04714). [blurring effect](https://arxiv.org/abs/2103.06191)
3. We definitely need to advocate for ourselves.
4. Cleaning up the system can be time-consuming and a headache.

