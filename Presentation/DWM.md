## Diffusion World Model: Future Modeling Beyond Step-by-Step Rollout for Offline Reinforcement Learning

In this paper, Zihan et al. introduce Diffusion World Model (DWM), a conditional diffusion model capable of predicting multistep future states and rewards concurrently. 
To evaluate the proposed DWM, the authors use an offline reinforcement learning setting, where policies are learned from a fixed dataset without online interaction. This removes exploration-related effects and enables a clearer assessment of world model quality. 
The authors first train a diffusion world model on offline data, then use its generated trajectories to train an actor-critic policy. They also introduce Diffusion-MVE, which estimates target values by simulating future trajectories up to a chosen horizon.


### Architecture
1. The Diffusion World Model (DWM) takes the current state, action, and target Return-to-Go (RTG) as inputs.

2. It predicts future state-reward trajectories rather than future actions, generating an 8-step future trajectory.

3. The core of DWM is a Temporal U-Net composed of residual convolutional blocks for sequence modeling.

4. The diffusion step, RTG, and initial action are encoded into latent embeddings using MLPs.

5. These embeddings are combined and used to condition the diffusion model during trajectory generation.

6. Through a guided diffusion process, the model generates future state and reward sequences that are used for planning and policy learning.

### Results
Zihan et al.'s results confirm that DWM outperform one-step models, where DWM-based algorithms achieve a 44% performance gain. 
They further consider a variant of their approach where the diffusion model is substituted with a Transformer architecture. They confirm that DWM-based algorithms surpass
Transformer-based algorithms with a 37.5% performance gain.
