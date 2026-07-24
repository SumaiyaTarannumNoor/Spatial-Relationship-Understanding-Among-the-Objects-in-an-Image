## Semantic Tube Prediction: Beating LLM Data Efficiency with JEPA
In this paper, Hai et al. propose a novel Semantic Tube Prediction (STP) task, a JEPA-style regularizer that confines hidden-state trajectories to a tubular neighbourhood of geodesic. STP generalizes JEPA to language without requiring explicit multi-view augmentation. 
Their main contributions are:
1. The authors introduce the Geodesic Hypothesis, which assumes that token sequences follow smooth semantic trajectories that are locally linear in latent space.
2. They propose Semantic Tube Prediction (STP), a JEPA-style regularizer that constrains hidden-state trajectories to remain within a semantic tube around the underlying geodesic.
3. They generalize JEPA to language modeling without requiring explicit multi-view augmentations.
4. They demonstrate substantially improved data efficiency, challenging the data-efficiency limits suggested by Chinchilla-style scaling laws.
