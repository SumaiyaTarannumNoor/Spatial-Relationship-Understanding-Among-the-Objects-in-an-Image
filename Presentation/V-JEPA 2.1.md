## V-JEPA 2.1: Unlocking Dense Features in Video Self-Supervised Learning
In this paper, Lorenzo et al. present  V-JEPA 2.1, a family of self-supervised models that learn dense, high-quality representations of visual scenes in both images and videos, with strong global scene understanding.  
V-JEPA 2.1 combined 4 key ingedients:
- a Dense Predictive Loss, a masking-based objective in which all tokens—visible context and masked tokens alike—contribute to the training loss, encouraging explicit spatial and temporal grounding
-  Deep Self-Supervision, which applies the self-supervised objective hierarchically at multiple intermediate encoder layers to improve representation quality
- Multi-Modal Tokenizers that support unified training over images and videos
- effective model and data scaling
