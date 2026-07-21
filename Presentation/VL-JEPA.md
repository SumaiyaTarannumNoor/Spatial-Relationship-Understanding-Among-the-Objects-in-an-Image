## VL-JEPA: Joint Embedding Predictive Architecture for Vision-language
Delong et al. introduce VL-JEPA, a vision-language model built on the JEPA architecture that predicts continuous embeddings of target texts. By learning in an abstract representation space, the model focuses on task-relevant semantics while abstracting away surface-level linguistic variability.
In this paper, Delong et al. gives a summery of their contributions:
- They introduce VL-JEPA, the first non-generative model that can perform general-domain vision language tasks in real-time, built on a joint-embedding predictive architecture.
- They demonstrate in controlled experiments that VL-JEPA, trained with latent space embedding prediction, outperforms VLMs that rely on data space token prediction.
- They show that VL-JEPA delivers significant efficiency gains over VLMs for online video streaming applications, thanks to its non-autoregressive design and native support for selective decoding.
- They highlight that their VL-JEPA<sub>SFT</sub> model with a unified model architecture can effectively handle a wide range of classification, retrieval, and VQA tasks at the same time.
