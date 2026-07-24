## Diffusion for World Modeling: Visual Details Matter in Atari
In this paper, Eloi et al. introduce **DIAMOND** (Diffusion As a Model of eNvironment Dreams), a reinforcement learning agent trained in a diffusion world model. They analyze the key design choices that are required to make diffusion stable for world modeling, and demonstrate how improved visual details can lead to improved agent performance.

### Architecture
- The architecture is built around a diffusion-based world model called DIAMOND.
- The world model predicts future observations directly in pixel space using a diffusion process rather than discrete latent tokens.
- The diffusion model is conditioned on previous observations and agent actions to generate future environment states.
- An RL agent is trained entirely inside the generated environment produced by the world model.
- The authors employ the EDM (Elucidated Diffusion Model) framework to improve generation quality and stability.
- The generated trajectories are used to train policies without requiring additional interaction with the real environment.

### Evaluation 
Eloi et al. evaluated DIAMOND on the Atari 100k benchmark, a standard sample-efficient reinforcement learning benchmark where agents are limited to 100,000 interactions with the environment. They compared DIAMOND against several state-of-the-art world-model-based reinforcement learning approaches, including SimPLe, TWM, IRIS, DreamerV3, and STORM. The evaluation used Human Normalized Score (HNS) and Interquartile Mean (IQM) as the primary performance metrics.

### Results
Eloi et al. report that DIAMOND achieved a mean Human Normalized Score (HNS) of 1.46 and an Interquartile Mean (IQM) of 0.64 on the Atari 100k benchmark. The model outperformed human players on 11 Atari games and achieved a new state-of-the-art result among agents trained entirely within a world model. The authors also observed particularly strong performance on visually demanding games such as Asterix, Breakout, and Road Runner, demonstrating the importance of preserving visual details during world modeling.
