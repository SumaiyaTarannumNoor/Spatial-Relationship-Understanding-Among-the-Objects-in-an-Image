## Self-Supervised Video Models Enable Understanding, Prediction and Planning

   In this paper, Assran et al. explored a self-supervised approach that combines internet-scale video data with a small amount of interaction data (robot trajectories), to develop models capable of planning, predicting and acting in the physical world. 

In this work, the authors build upon the self-supervised hypothesis as a means to learn world models that capture background knowledge of the world largely from observation. Specifically, they leverage the Joint Embedding Predictive Architecture  (JEPA), which learns by making predictions in a learned representation space. 

For V-JEPA 2, Assran et al. utilize a stage-wise training procedure, beginning with action-free pre-training on internet-scale video, followed by post-training with a small amount of interaction data. In the first stage, they use a mask-denoising feature prediction objective, where the model segments of a video in a learned representation space. They train the V-JEPA 2 encoder with up to 1 billion parameters and with more than 1 million hours of video.

After the pretraining on internet-scale video, they trained an action-conditioned world model, V-JEPA 2-AC, on a small set of interaction data using the representations learned from the first stage. This action-conditioned world model is a 300M-parameter transformer network employing a block-casual attention mechanism, which autoregressively predicts the representation of the next video frame conditioned on an action and previous states. 
 
