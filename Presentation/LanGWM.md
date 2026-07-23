## LanGWM: Language Grounded World Model
In this paper, Rudra et al., focus on learning language-grounded visual features to enhance the world model learning, a model-based reinforcement learning technique. The authors explore a representation-learning architecture for RL that improves visual features with the help of language.
Rudra et al. proposed the Language Grounded World Model (LanGWM), which enforces language grounding explicitly to improve the generalization of the learned visual features.
In summary, their contributions are two-fold:
- A novel explicitly language grounded visual representation learning method, which outperforms state-of-the-art models on visual control tasks.
- An efficient alternative to visual foundation models for autonomous systems with limited resources.

### Architecture
LanGWM consists of three main components:
1. Unsupervised language grounded representation learning: This uses the object masking-based masked autoencoder.
2. World Model: The world model uses a recurrent neural network to output the parameters of a categorical distribution, which is used to sample the future states of the environment.
3. Controller: The controller learns the action probability using an actor-critic approach, which maximises the expected reward.

### Evaluation
Rudra et al. evaluated LanGWM's performance on the PointGoal navigation task using the iGibson 1.0 dataset for out-of-distribution generalisation performance. They reported Success Rate (SR) and Success weighted by (normalized inverse) Path Length (SPL). LanGWM achieved 8.3 SR and 0.05 SPL for Ihlen_0_int environment; 2.1 SR and 0.01 SPL for Iheln_1_int environment; 9.9 SR and 0.06 SPL for RS_int environment. The average SR for LanGWM is 6.8, and the average SPL for LanGWM is 0.04.
