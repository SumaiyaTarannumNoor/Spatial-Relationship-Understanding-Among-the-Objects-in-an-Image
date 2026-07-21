## Video World Models with Long-term Spatial Memory
In this paper, Tong et al. introduced a novel framework to enhance long-term consistency or video world models through a geometry-grounded long-term spatial memory and they curated custom datasets to train and evaluate world models with explicitly stored 3D memory mechanism.
Their Approach incorporates three distinct forms of memory: spatial, working and episodic- each modeled through a dedicated representation. Their framework relies on a set of recently generated context frames. 

### Architecture
Their system is a latent video generation model implemented with a Diffusion Transformer (DiT) and conditioned on three different memory mechanisms during autoregressive frame generation. First, recent context frames model a short-term working memory. Second, a point cloud representation is autoregressively generated along with the video frames. This long-term spatial memory contains the static parts of the world. Third, a set of historical reference frames is stored as a sparse, long-term episodic memory. Together, these memory mechanisms enable consistent long-term video generation.  

Tong et al.'s prototype implementation builds on CogVideoX, which adopts this two-stage framework. Specifically, CogVideoX employs a diffusion transformer with 3D attention blocks to capture the distribution of the latent space. Their model improves upon this architecture with additional control signals for enabling long-term memory.


### Dataset
They built their own dataset from raw videos collected from MiraData, segmenting each video into multiple 97-frame clips. For each clip, the first 49 frames serve as the source sequence and the remaining 48 as the target, with a shared transition frame to preserve temporal continuity. To recover scene geometry, they performed 4D reconstruction using Mega-SaM, extracting camera intrinsics, extrinsics, and per-frame depth maps. They applied TSDF-Fusion to the source frames, integrating RGB-D observations into a volumetric grid.


### Evaluation
The model has achieved 19.10 for PSNR (Peak Signal-to-Noise Ratio), 0.6471 for SSIM (Structural Similarity Index Measure), and 0.3069 for LPIPS (Learned Perceptual Image Patch Similarity, 0.36260 for camera accuracy 
