## Diffusion for World Modeling: Visual Details Matter in Atari
In this paper, Eloi et al. introduce **DIAMOND** (Diffusion As a Model of eNvironment Dreams), a reinforcement learning agent trained in a diffusion world model. They analyze the key design choices that are required to make diffusion stable for world modeling, and demonstrate how improved visual details can lead to improved agent performance.

### Architecture
- The architecture is built around a diffusion-based world model called DIAMOND.
- The world model predicts future observations directly in pixel space using a diffusion process rather than discrete latent tokens.
- The diffusion model is conditioned on previous observations and agent actions to generate future environment states.
- An RL agent is trained entirely inside the generated environment produced by the world model.
- The authors employ the EDM (Elucidated Diffusion Model) framework to improve generation quality and stability.
- The generated trajectories are used to train policies without requiring additional interaction with the real environment.
