## Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture

In this paper, Assran et al. present the idea of I-JEPA (Image-based Joint Embedding Predictive Architecture), which is a non-generative approach for self-supervised learning from images to learn highly semantic image representation without relying on hand-crafted data augmentations.
The idea behind I-JEPA is simple: from a single context block, predict the representations of various target blocks in the same image.
In this work, the authors explore the way to improve the semantic level of self-supervised representations without using extra prior knowledge encoded through image transformations. The main idea behind I-JEPA is to predict the missing information in an abstract representation space. I-JEPA's approach is comparatively better than generative methods, therefore the unnecessary pixel-level details are dropped. 
Through an extensive empirical evaluation, Assran et al. demonstrate that: 
- I-JEPA can learn from off-the-shelf representations without hand-crafted view augmentations.
- I-JEPA is competitive with view-invariant pretraining approaches on semantic tasks and achieves better performance on low-level vision tasks such as object counting and depth prediction.
- I-JEPA is also scalable and efficient.

### Architecture
I-JEPA uses the basic architecture of JEPA, which is conceptually similar to Generative models. JEPAs learn to predict the embeddings of a signal y from a compatible signal x, using a predictor network that is conditioned on an additional (possibly latent) variable z to facilitate prediction. Their proposed I-JEPA model provides an instantiation of this architecture in the context of images using masking. 

The I-JEPA uses a single context block to predict the representations of various target blocks originating from the same image. The context encoder is a Vision Transformer (ViT), which only processes the visible context patches. The predictor is a narrow ViT that takes the context encoder output and, conditioned on positional tokens, predicts the representation of a target block at a specific location. The target representation corresponds to the outputs of the target-encoder, the weights of which are updated at each iteration via an exponential moving average of the context encoder weight. 

### Evaluation
-The I-JEPA was evaluated on ImageNet-1% for semi-supervised evaluation, where the I-JEPA's 3 architecture achieved significant performance. I-jepa architecture ViT-L/16 achieved Top-1 of 69.4 for 600 epochs, ViT-H/14 achieved 73.3 for 300 epochs, and ViT-H/16<sub>444</sub> achieved 77.3 for 300 epochs. 
- For Linear evaluation on the downstream image classification task, I-JEPA's ViT-H/14 achieved 87.5 on CIFAR10, 58.4 on Places205 and 47.6 on iNet18.
- For Linear evaluation on downstream low-level tasks, I-JEPAs ViT-H/14 achieved 86.7 on the Clevr dataset for object counting and 72.4 for depth prediction.
