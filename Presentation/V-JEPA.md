## Revisiting Feature Prediction for Learning Visual Representations from Video

In this paper, Adrien et al. use unsupervised learning from videos for feature prediction as a stand-alone objective. They introduce V-JEPA or Video Joint Embedding Predictive Architectures. In this paper, the authors present their Model, V-JEPA, a comparatively better solution than pixel prediction models. In essence, V-JEPA is trained with an objective of feature prediction, which is far superior to the models that either predict or reconstruct the pixels.

### Architecture
Adrien et al. used the JEPA or Joint embedding predictive architecture as the base model to train on videos. The basic JEPA architecture is made up of an encoder, which computes the representation of the inputs, and a predictor, which predicts the representation of the target from the representation of the input, conditioned on a variable indicating the transformation between the input and the target. Conditioning on a variable enables the generation of distinct predictions for various transformations of the input. 

Their training objective was to satisfy the constraint that representations computed from one part of the target video should be predictable from representations computed from another part of the input video. 

Predicting target from input: To predict the target from the input, the authors used a masked modeling formulation. 
They leverage two types of masks: One  that is the union of 8 randomly sampled target blocks covering 15% of each frame. Another one is the union of 2 randomly sampled target blocks, each covering 70% of a frame. In both cases, the aspect ratio for all sampled blocks is randomly chosen in the range (0.75, 1.5). As they have used both short-ranged and long-ranged masks by sampling many blocks and taking their union, the result is an average masking ratio of ~90%.

Adrien et al. use a Vision Transformer (ViT) to process a video.

### Dataset
Adrien et al. combined several public datasets to construct an unsupervised video pretraining dataset, which they refer to as **VideoMix2M**. Specifically, they combined the videos from HowTo100M (HT), Kinetics-400/600/700 (K710) and Something-Something-v2 (SSv2), resulting in approximately 2 million videos.

### Evaluations
The authors of this paper evaluated the pre-trained models on downstream video and image tasks. On video tasks, they used a subset of the VideoGLUE benchmark to test the various capabilities; specifically, they investigated action recognition on Kinetics-400 (K400), motion classification on Something-Something-v2 (SSv2) and action localization on AVA.
All models are pretrained on VideoMix2M for 90K iterations with a batch size of 3072 using multi-block masking. They examined performance on Kinetics-400 (K400), Something-Something-v2 (SSv2), and ImageNet-1K(IN1K), using a frozen backbone with an attentive probe, and report top-1 accuracy using a single centre view. They also examined end-to-end fine-tuning performance of the models on Kinetics-400.
