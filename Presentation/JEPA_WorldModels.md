## VALUE-GUIDED ACTION PLANNING WITH JEPA WORLD MODELS
In this paper, Matthieu et al. proposed improving planning in JEPA-based world models by shaping the representation space so that the distance between state embeddings reflects the goal-conditioned value function. They introduce a training method that enforces this property and demonstrate that it significantly improves planning performance compared to standard JEPA models on simple control tasks.

### Architecture 
1. States are encoded into 512-dimensional latent representations using a convolutional encoder with residual connections.

2. Actions are processed through an identity action encoder without additional transformations.

3. State and action representations are concatenated before being passed to the predictor.

4. An MLP-based predictor learns future state representations in the latent space.

5. The architecture contains a 2.2M-parameter encoder and a 1.3M-parameter predictor.

6. Training is performed on trajectory segments of length 16.

7. The learned representations are shaped so that distances between embeddings approximate the goal-conditioned value function, improving planning performance.
