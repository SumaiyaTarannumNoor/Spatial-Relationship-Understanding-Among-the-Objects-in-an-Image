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

### Evaluation
The authors evaluated their approach in an offline reinforcement learning setting using image-based navigation tasks in the Wall Small (WS), Wall Big (WB), and Maze environments. Planning performance was measured using planning accuracy, and the proposed value-function-guided JEPA representations were compared against contrastive, regressive, and standard prediction-based JEPA approaches.

### Results
Matthieu et al. report that the VF quasi approach achieved the highest planning accuracies across all environments, reaching 0.71 in WS, 0.96 in WB, and 0.63 in Maze. These results outperform standard prediction-based JEPA methods and highlight the benefits of value-function-guided representations for planning.

### Results
The VF quasi approach achieved the best planning performance across all environments, with planning accuracies of 0.71 in WS, 0.96 in WB, and 0.63 in Maze. These results outperformed the standard prediction-based JEPA approach, which achieved accuracies of 0.55, 0.89, and 0.54 respectively, demonstrating the effectiveness of value-function-guided representations for planning.
