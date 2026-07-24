## VALUE-GUIDED ACTION PLANNING WITH JEPA WORLD MODELS
In this paper, Matthieu et al. proposed improving planning in JEPA-based world models by shaping the representation space so that the distance between state embeddings reflects the goal-conditioned value function. They introduce a training method that enforces this property and demonstrate that it significantly improves planning performance compared to standard JEPA models on simple control tasks.

### Architecture 
1. The architecture uses 512-dimensional latent representations for states.

2. The state encoder is built using convolutional layers with residual connections.

3. An identity action encoder is used, meaning actions are passed directly without additional encoding.

4. State and action representations are concatenated before prediction.

5. A Multi-Layer Perceptron (MLP) predictor is used to predict future representations.

6. The architecture consists of a 2.2M-parameter encoder and a 1.3M-parameter predictor.

7. Training is performed on trajectory segments of length 16.
   
