## Diffusion World Model: Future Modeling Beyond Step-by-Step Rollout for Offline Reinforcement Learning





### Architecture
1. The Diffusion World Model (DWM) takes the current state, action, and target Return-to-Go (RTG) as inputs.

2. It predicts future state-reward trajectories rather than future actions, generating an 8-step future trajectory.

3. The core of DWM is a Temporal U-Net composed of residual convolutional blocks for sequence modeling.

4. The diffusion step, RTG, and initial action are encoded into latent embeddings using MLPs.

5. These embeddings are combined and used to condition the diffusion model during trajectory generation.

6. Through a guided diffusion process, the model generates future state and reward sequences that are used for planning and policy learning.
