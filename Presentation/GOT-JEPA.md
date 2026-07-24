## GOT-JEPA: Generic Object Tracking with Model Adaptation and Occlusion Handling using Joint-Embedding Predictive Architecture

In this paper, Shih-Fang et al. propose GOT-JEPA, a model-predictive pre-training framework that extends JEPA from predicting image features to predicting tracking models.
Their main contributions are:

GOT-JEPA, a JEPA-based framework that learns to predict tracking models rather than image features.
A teacher-student predictive learning strategy that improves robustness to occlusions, distractors, and appearance variations.
OccuSolver, a module for fine-grained object-aware visibility estimation and occlusion pattern modeling.
Strong improvements in tracking robustness and generalization across multiple tracking benchmarks.

### Architecture
1. Historical frames and previous tracking results are used as few-shot examples to provide context about the target object.
2. A Teacher Predictor (t-Predictor) receives a clean current frame and generates pseudo-tracking models.
3. A Student Predictor (s-Predictor) receives a corrupted version of the same frame and learns to predict the teacher's pseudo-tracking models.
4. Both teacher and student predictors share the same historical information, allowing the student to learn robust model adaptation under challenging conditions.
5. The framework extends JEPA from image-feature prediction to tracking-model prediction.
