## Video World Models with Long-term Spatial Memory
In this paper, Tong et al. introduced a novel framework to enhance long-term consistency or video world models through a geometry-grounded long-term spatial memory and they curated custom datasets to train and evaluate world models with explicitly stored 3D memory mechanism.
Their Approach incorporates three distinct forms of memory: spatial, working and episodic- each modeled through a dedicated representation. Their framework relies on a set of recently generated context frames. 

### Architecture
Their system is a latent video generation model implemented with a Diffusion Transformer (DiT) and conditioned on three different memory mechanisms during autoregressive frame generation. First, recent context frames model a short-term working memory. Second, a point cloud representation is autoregressively generated along with the video frames. This long-term spatial memory contains the static parts of the world. Third, a set of historical reference frames is stored as a sparse, long-term episodic memory. Together, these memory mechanisms enable consistent long-term video generation.  

Tong et al.'s prototype implementation builds on CogVideoX, which adopts this two-stage framework. Specifically, CogVideoX employs a diffusion transformer with 3D attention blocks to capture the distribution of the latent space. Their model improves upon this architecture with additional control signals for enabling long-term memory.
