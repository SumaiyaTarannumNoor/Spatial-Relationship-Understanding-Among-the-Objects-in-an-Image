## A GENERALIZATION THEORY FOR JEPA-BASED WORLD MODELS
In this paper, Jingyi et al. develop the first generalization theory for JEPA-based world models. They formulate JEPA pretraining as a conditional spectral graph learning problem and show that the JEPA objective is equivalent to a low-rank factorization of an action-conditioned co-occurrence matrix.
Their main contributions are:
• The authors introduce a spectral graph-based theoretical framework for JEPA-based world models using an action-conditioned state co-occurrence matrix.

• They show that JEPA training can be interpreted as factorizing this action-conditioned co-occurrence matrix and derive a generalization error bound for JEPA-based world models.

• Their analysis reveals a trade-off between approximation error and sample error with respect to latent dimensionality, providing theoretical insights into the strengths of latent-level and input-level predictive models.

### Approach
Rather than proposing a new world model architecture, Jingyi et al. develop the first theoretical framework for JEPA-based world models. They formulate JEPA learning as a conditional spectral graph problem using an action-conditioned co-occurrence matrix, show that JEPA training is equivalent to low-rank matrix factorization, and derive generalization bounds linking pretraining error to downstream planning regret. Their analysis also reveals a trade-off between latent dimensionality, approximation error, and sample efficiency, providing theoretical insights into the strengths and limitations of latent predictive world models.
