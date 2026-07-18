## Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture

In this paper, Assran et el. present the idea of I-JEPA (Image-based Joint Embedding Predictive Architecture), which is a non-generative approach for self-supervised learning from images to learn highly semantic image representation without relying on hand-crafted data augmentations.
The idea behind I-JEPA is simple: from a single context block, predict the representations of various target blocks in the same image.
In this work, the authors explore the way to improve the semantic level of self-supervised representations without using extra prior knowledge encoded through image transformations. The main idea behind I-JEPA is to predict the missing information in an abstract representation space. I-JEPA's approach is comparatively better than generative methods, therefore the unnecessary pixel-level details are dropped. 
Through an extensive empirical evaluation, Assran et el. demonstrate that: 
- I-JEPA can learn from off-the-shelf representations without hand-crafted view augmentations.
- I-JEPA is competitive with view-invariant pretraining approaches on semantic tasks and achieves better performance on low-level vision tasks such as object counting and depth prediction.
- I-JEPA is also scalable and efficient.
