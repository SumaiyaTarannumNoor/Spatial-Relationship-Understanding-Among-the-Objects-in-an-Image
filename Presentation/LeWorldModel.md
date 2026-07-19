## LeWorldModel: Stable End-to-End Joint-Embedding Predictive Architecture from Pixels 
In this paper, Lucas et al. introduce LeWorldmodel (LeWM), which, according to their claim, first JEPA that trains stably end-to-end from raw pixels using only two loss terms: a next-embedding prediction loss and a regularizer enforcing Gaussian-distributed latent embeddings. The authors evaluated LeWM across a diverse set of manipulation, navigation, and locomotion tasks in both 2D and 3D environments. In addition, they probed its intuitive physical understanding through targeted probing and surprise-quantification evaluations in latent space. Their Key findings are:
- They proposed an end-to-end JEPA method for learning a latent world model from raw pixels on a single GPU. The method relies on a simple and stable two-term objective that remains robust across architectures and hyperparameter choices, while enabling efficient logarithmic-time hyperparameter search.
- Their experiment demonstrated that LeWM achieved competitive control performance across diverse 2D and 3D tasks with only a compact 15M-parameter model, surpassing existing end-to-end JEPA-based approaches while remaining competitive with foundation-model-based world models at substantially lower cost, enabling planning up to 48x faster.

### Architecture
 Lewm is built with two components: an encoder and a predictor. The encoder maps a given frame observation o<sub>t</sub> into a compact low-dimensional latent representation z<sub>t</sub>. The predictor models the environment dynamics in latent space by predicting the embedding of the next frame observation z<sub>t+1</sub> given the latent embedding z<sub>t</sub> and an action a<sub>t</sub>. 
 
```
Encoder: z<sub>t</sub> = enc<sub>θ</sub>(o<sub>t</sub>)
Predictor: z<sub>t+1</sub> = pred<sub>ϕ</sub> (z<sub>t</sub>, a<sub>t</sub>)
```
The encoder is implemented as a vision transformer (ViT). In general, the authors used the tiny configuration (~5M parameters) with a patch size of 14, 12 layers and 3 attention heads, and hidden dimensions of 192. The observation embedding z<sub>t</sub> is constructed from the [CLS] token embedding of the last layer, followed by a projection step. The projection step maps the [CLS] token embedding into a new representation space using a 1-layer MLP with Batch Normalization. This step is necessary because the final ViT layer applies a Layer Normalization, which prevents their anti-collapse objective from being optimized effectively.
