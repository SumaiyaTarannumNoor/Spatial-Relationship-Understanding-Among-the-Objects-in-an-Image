## LLM-JEPA: LARGE LANGUAGE MODELS MEET JOINT EMBEDDING PREDICTIVE ARCHITECTURES
In this paper, Hai et al. propose a first step in the direction of developing LLM-JEPA, a JEPA-based solution for LLMs applicable for both finetuning and pretraining. Thus far, LLM-JEPA is able to outperform the standard LLM training objectives by a significant margin across models, all while being robust to overfitting. 

Their main contributions are:
- **Novel JEPA-based training objective**: They present the first JEPA-based training objective for LLMs operating in embedding space and with different views, perfectly following vision-based JEPAs without sacrificing the generative capabilities of LLMs.
- **Improved SOTA**: They empirically validate their formulation in various fine-tuning settings, where they obtain improvements over standard LLM fine-tuning solutions. They also explore pretraining scenarios, showing encouraging results of LLM-JEPA
- **Extensive empirical validation**: On various model family (llama, gemma, apple/openelm, allenai/olmo), datasets (NL-RX, GSM8K, Spider, RottenTomatoes), and size

### Architecture
The construction of our LLM-JEPA objective relies on two principles. First, the generative capabilities of LLMs must be preserved, and Second, it should be aimed
to improve the abstraction capabilities of LLMs using the joint embedding prediction task.
Therefore, the architecture includes: 
1. A standard autoregressive LLM serves as the backbone model.

2. An encoder extracts latent embeddings from text sequences using the final hidden representation.

3. A predictor network maps the input text embedding to the embedding of a target text.

4. The target text is encoded to provide the prediction target in the latent space.

5. Training combines the conventional next-token prediction objective with a JEPA embedding prediction objective.

6. The model learns both generative capabilities and abstract semantic representations through the joint training objective.
