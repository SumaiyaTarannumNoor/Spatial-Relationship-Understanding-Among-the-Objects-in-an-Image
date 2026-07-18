## Video Representation Learning with Joint-Embedding Predictive Architecture

In this paper, Katrina et el. present Video JEPA with Variance-Covariance Regularization (VJ-VCR): a joint embedding predictive architecture for self-supervised video representation learning that employs variance and covariance regularization to avoid representation collapse. They explore different ways to incorporate latent variables into the VJ-VCR framework that capture information about uncertainty in the future in non-deterministic settings.
Self-supervised learning for videos enables models to learn and extract high-level, information-rich features from videos without external annotations. In this way, models can capture complex temporal dynamics and semantic information directly from raw video data.
Generative models are used for pretext tasks where they make predictions in the input pixel space. JEPA or Joint embedding predictive architecture is an alternative to these generative models.
In particular, in JEPA the prediction occurs in the abstract space instead of pixel space, which is less computationally expensive.
There is a key challenge in training JEPA: preventing collapse in the hidden representations.
To prevent this collapse, Katrina et el. proposes a JEPA model that applies varience-covarience regularization to the model's hidden representations. They call this model Video JEPA with Variance-Covariance Regul;arization (VJ-VCR).
Presenting an alternate way for generative models in terms of predicting future and demonstrating VJ-VCR for capturing high-level information from videos are two main contributions of this paper. Two more contributions are: The outperformance of VJ-VCR from generative models on several downstream tasks and proposing ways to incorporate latent variables in the VJ-VCR setup that capture the information about future uncertainty.

### Architecture
The VJ-VCR model has two main parts - Encoder and Predictor, and it can also incorporate a Latent variable.
The Encoder maps all the input frames and target frames from the video. In order to prevent collapse in the representation space, they apply variance-covariance regularization.
The Predictor takes the hidden states of the input frames and predicts the hidden states of the target frames.
VJ-VCR incorporates a latent variable in order to facilitate the prediction task in case the target frames are not completely deterministic versions of the input.

### Experiments
To evaluate their model VJ-VCR Katrina et el. have performed for types of experiments. 
Those are: 
1. Generative Model Baseline: They use general generative model baselines, such as the difference in generative model architecture versus VJ-VCR architecture and similarity in incorporating a latent variable.
2. They validated their approach on two types of datasets:
   - deterministic datasets: MovingMNIST and CLEVR datasets
   - and non-deterministic datasets: They made their custom stochastic version of MovingMNIST and also used CATER, a dataset based on CLEVR
  
### Results

- Deterministic Setting:
1. MovingMNIST: The first two VJ-VCR model achieved MSE of 0.04, which indicates that JEPA models trained to make predictions in the abstract representations space outperform purely generative models at capturing the dynamics of moving  digits. The third one achieved MSE of 0.15.
2. CLEVR: On the CLEVR dataset, they evaluated the models based on RankMe. Among the first two models, the one trained with a decoder got a lower RankMe score of 359.8, and the one without a decoder got a RankMe score of 427.4.
- Non-deterministic Settings:
1. MovingMNIST: They observed that the discrete latent variables can predict the trajectory switch with 80% accuracy on average.
2. CATER: On this dataset the VJ-VCR outperforms generative models for 13.6% in how effectively latent variables capture information CATER moving objects.
