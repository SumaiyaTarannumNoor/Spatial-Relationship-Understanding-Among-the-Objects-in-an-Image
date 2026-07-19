## Self-Supervised Video Models Enable Understanding, Prediction and Planning

   In this paper, Assran et al. explored a self-supervised approach that combines internet-scale video data with a small amount of interaction data (robot trajectories), to develop models capable of planning, predicting and acting in the physical world. 

In this work, the authors build upon the self-supervised hypothesis as a means to learn world models that capture background knowledge of the world largely from observation. Specifically, they leverage the Joint Embedding Predictive Architecture  (JEPA), which learns by making predictions in a learned representation space. 

For V-JEPA 2, Assran et al. utilize a stage-wise training procedure, beginning with action-free pre-training on internet-scale video, followed by post-training with a small amount of interaction data. In the first stage, they use a mask-denoising feature prediction objective, where the model segments of a video in a learned representation space. They train the V-JEPA 2 encoder with up to 1 billion parameters and with more than 1 million hours of video.

After the pretraining on internet-scale video, they trained an action-conditioned world model, V-JEPA 2-AC, on a small set of interaction data using the representations learned from the first stage. This action-conditioned world model is a 300M-parameter transformer network employing a block-casual attention 
mechanism, which autoregressively predicts the representation of the next video frame conditioned on an action and previous states. 

### Architecture
In the architecture of V-JEPA 2, the Encoder and the Predictor are each parameterized as a vision transformer (ViT). To encode relative position information in the vision transformer, they leveraged RoPE (Rotary Position Embedding) instead of the absolute sincos position. They use a 3D extension of traditional 1S-RoPE by partitioning the feature dimension into three approximately equal segments (for the temporal, height and width axes) and applying the 1D rotations separately to the segment for each axes. 
 
Assran et al. have used some key scaling ingredients for scaling V-JEPA pre-training principle to obtain V-JEPA 2 model.
1. Data scaling: They increased the dataset size from 2 million to 22 million videos by leveraging and curating additional data sources.
2. Model Scaling: The scaled the encoder architecture from 300 million to over 1 billion parameters, going from ViT-L to ViT-g.
3. Longer Training: Adopted a warmup-constant-decay learning rate schedule simplifies hyperparameter tuning and enabled them to extend training from 90 thousand to 252 thousand iterations, effectively leveraging the additional data.
4. Higher Resolution: They leveraged the warmup-constant-decay schedule to efficiently scale to higher resolution video and longer video clips by training on shorter, lower-resolution clips during the warmup and constant phases, and then increasing resolution and/or clip-length during the final decay phase.

### Evaluation
They divided their evaluation process into different classes: understanding, prediction and planning.
- Understanding:
   1. Probe-based Classification: Scaling self-supervised video pretraining results in video representations applicable to many tasks. V-JEPA 2 excels at encoding fine-grained motion information, achieving strong performance on tasks requiring motion understanding, such as Something-Something v2, with 77.3 top-1 accuracy using an attentive probe.
   2. Video-Question Answering: V-JEPA 2 encoder can be used to train a multi-modal large language model, to tackle video-question answering tasks. They observed state-of-art performance on 8B language model class on multiple benchmarks that require physical world understanding and temporal reasoning. In particular, they showed that a video encoder pre-trained without language supervision can be aligned with a language model and achieve state-of-art performance, contrary to conventional wisdom.
- Prediction: Large-scale self-supervised video pretraining enhances prediction capabilities. V-JEPA 2 achieves state-of-art performance on the Epic-Kitchens-100 human-action anticipation task using an attentive probe, with 39.7 recall-at-5, which is a 44% relative improvement over the previous best model.
- Planning: They demonstrate that V-JEPA 2-AC, obtained by post-training V-JEPA 2 with 62 hours of unlabled robot manipulation data from the popular Droid dataset, can be deployed in new environments to solve prehensile manipulation tasks using planning with given subgoals. 
