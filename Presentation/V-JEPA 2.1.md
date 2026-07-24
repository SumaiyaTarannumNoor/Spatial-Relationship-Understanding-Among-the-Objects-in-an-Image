## V-JEPA 2.1: Unlocking Dense Features in Video Self-Supervised Learning
In this paper, Lorenzo et al. present  V-JEPA 2.1, a family of self-supervised models that learn dense, high-quality representations of visual scenes in both images and videos, with strong global scene understanding.  
V-JEPA 2.1 combined 4 key ingedients:
- a Dense Predictive Loss, a masking-based objective in which all tokens—visible context and masked tokens alike—contribute to the training loss, encouraging explicit spatial and temporal grounding
-  Deep Self-Supervision, which applies the self-supervised objective hierarchically at multiple intermediate encoder layers to improve representation quality
- Multi-Modal Tokenizers that support unified training over images and videos
- effective model and data scaling

### Architecture
1. Images and videos are processed using 2D or 3D convolutional patch embeddings.
2. 3D RoPE (Rotational Positional Encoding) and modality embeddings are added, and the encoder generates multi-level visual representations.
3.  An MLP fuses the multi-level features, reduces dimensionality, and combines them with learnable mask tokens.
4. The predictor processes the combined tokens and generates predictions for the masked regions.
5. Training uses two different losses: (i) an L1 loss on masked-token predictions (the original V-JEPA objective),
and (ii) a distance-weighted L1 loss on nearby context tokens, both supervised using the y-encoder multi-level outputs.
