## VL-JEPA: Joint Embedding Predictive Architecture for Vision-language
Delong et al. introduce VL-JEPA, a vision-language model built on the JEPA architecture that predicts continuous embeddings of target texts. By learning in an abstract representation space, the model focuses on task-relevant semantics while abstracting away surface-level linguistic variability.
In this paper, Delong et al. give a summary of their contributions:
- They introduce VL-JEPA, the first non-generative model that can perform general-domain vision language tasks in real-time, built on a joint-embedding predictive architecture.
- They demonstrate in controlled experiments that VL-JEPA, trained with latent space embedding prediction, outperforms VLMs that rely on data space token prediction.
- They show that VL-JEPA delivers significant efficiency gains over VLMs for online video streaming applications, thanks to its non-autoregressive design and native support for selective decoding.
- They highlight that their VL-JEPA<sub>SFT</sub> model with a unified model architecture can effectively handle a wide range of classification, retrieval, and VQA tasks at the same time.

### Architecture
The VL-JEPA comprises four components:
1. X-Encoder: X-Encoder compresses high-volume visual inputs to compact visual embeddings - a sequence of continuous vectors analogous to "visual tokens" in classical VLMs.
2. Predictor: Predictor is the core component of VL-JEPA. It maps visual embeddings to a prediction of the target embedding, with a textual query as conditioning.
3. Y-Encoder: Y-Encoder embeds the textual target into a continuous latent space as the prediction target. The target embedding is expected to abstract away task-irrelevant information.
4. Y-Decoder: Y-Decoder is not involved during the main training phase of VL-JEPA. At inference time, it translates the predicted embedding as human-readable text when necessary.

The final VL-JEPA models are trained in two stages: 
 1. A pre-training stage using caption data to establish robust vision-language alignment, resulting in VL-JEPA<sub>BASE</sub>, and
 2. A supervised finetuning (SFT) stage that equips the model with VQA capabilities, resulting in VL-JEPA<sub>SFT</sub>.  

### Evaluation
VL-JEPA<sub>BASE</sub> achieved very good top-1 accuracy in 8 different datasets - 19.3 on SSv2, 21.8 on EK100, 33.2 on EgoExo4D, 64.8 on Kinetics-400, 47.4 on COIN (SR), 79.4 on COIN (TR), 64.5 on CrossTask (SR) and 89.6 on CrossTask (TR). VL-JEPA<sub>BASE</sub> also achieved very good Recall@1 on 8 different datasets - 40.0 on MSR-VTT, 64.9 on ActivityNet, 50.0 on DiDeMo, 49.0 on MSVD, 40.0 on YouCook2, 83.1 on PVD-Bench, 93.3 on Dream-1K and 88.8 on VDC-1K.

VL-JEPA<sub>SFT</sub> also achieved top-1 accuracy in 8 different datasets - 73.2 on SSv2, 44.6 on EK100, 68.1 on EgoExo4D, 84.8 on Kinetics-400, 66.4 on COIN (SR), 90.3 on COIN (TR), 79.8 on CrossTask (SR) and 96.2 on CrossTask (TR). VL-JEPA<sub>SFT</sub> also achieved Recall@1 on 8 different datasets - 46.2 on MSR-VTT, 62.4 on ActivityNet, 52.3 on DiDeMo, 52.3 on MSVD, 37.8 on YouCook2, 82.6 on PVD-Bench, 89.3 on Dream-1K and 87.7 on VDC-1K.
