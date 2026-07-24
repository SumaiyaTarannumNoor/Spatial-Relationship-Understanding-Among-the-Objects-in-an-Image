## Semantic Tube Prediction: Beating LLM Data Efficiency with JEPA
In this paper, Hai et al. propose a novel Semantic Tube Prediction (STP) task, a JEPA-style regularizer that confines hidden-state trajectories to a tubular neighbourhood of geodesic. STP generalizes JEPA to language without requiring explicit multi-view augmentation. 
Their main contributions are:
1. The authors introduce the Geodesic Hypothesis, which assumes that token sequences follow smooth semantic trajectories that are locally linear in latent space.
2. They propose Semantic Tube Prediction (STP), a JEPA-style regularizer that constrains hidden-state trajectories to remain within a semantic tube around the underlying geodesic.
3. They generalize JEPA to language modeling without requiring explicit multi-view augmentations.
4. They demonstrate substantially improved data efficiency, challenging the data-efficiency limits suggested by Chinchilla-style scaling laws.

### Architecture
The architecture consists of four main components:

1. Autoregressive LLM Backbone – generates hidden-state representations from token sequences.
2. Hidden-State Trajectory Modeling – treats successive hidden states as points on a semantic manifold.
3. Semantic Tube Prediction (STP) Module – constrains hidden-state trajectories to remain close to a locally linear geodesic path.
4. Joint Training Objective – combines standard next-token prediction with the STP regularization loss.
