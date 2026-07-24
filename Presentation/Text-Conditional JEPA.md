## Text-Conditional JEPA for Learning Semantically Rich Visual Representations
In this work, Chen et al. propose Text-Conditional JEPA (TC-JEPA) that uses image captions to reduce the prediction uncertainty. Text-Conditional JEPA (TC-JEPA) combines the predictive power of JEPAs with text conditioning inputs, which is under-explored in the context of visual representation learning. This way, they turned I-JEPA into a text-conditional representation learner, where patch representations are now predictable or transformable when "prompted" by text, thus are more language aligned and semantically meaningful. 
Their main contributions are:
1) They propose TC-JEPA to improve I-JEPA via fine-grained text conditioning, which in turn produces semantically rich visual representations. 
2) TC-JEPA leads to improved downstream performance, training stability and scaling properties. 
3) TC-JEPA offers a fine-grained vision-language pretraining paradigm based on feature prediction only, which outperforms contrastive methods on diverse (fine-grained) tasks.

### Architecture
There are four main architectural components:
1. Image Encoder (ViT) – extracts visual representations from visible image patches.
2. Target Encoder – generates target representations for masked image patches.
3. Predictor Network – predicts representations of masked patches from context features.
4. Text Conditioner – processes image captions and injects textual information into visual representations through cross-attention.

### Evaluation
Chen et al. evaluated TC-JEPA on visual and vision-language tasks using ImageNet-1K, CC12M, and YFCC15M. The model was compared against I-JEPA, MAE, data2vec, CLIP, and SigLIP using image classification, semantic segmentation, and vision-language benchmarks.

### Results
Chen et al. report that TC-JEPA consistently outperformed I-JEPA across different model scales. On ImageNet-1K linear probing, TC-JEPA achieved 80.4% Top-1 accuracy with ViT-H/14, compared to 79.3% for I-JEPA. The model also surpassed MAE and data2vec while demonstrating stronger semantic understanding and improved training efficiency.
