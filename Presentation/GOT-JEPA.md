## GOT-JEPA: Generic Object Tracking with Model Adaptation and Occlusion Handling using Joint-Embedding Predictive Architecture

In this paper, Shih-Fang et al. propose GOT-JEPA, a model-predictive pre-training framework that extends JEPA from predicting image features to predicting tracking models.
Their main contributions are:

GOT-JEPA, a JEPA-based framework that learns to predict tracking models rather than image features.
A teacher-student predictive learning strategy that improves robustness to occlusions, distractors, and appearance variations.
OccuSolver, a module for fine-grained object-aware visibility estimation and occlusion pattern modeling.
Strong improvements in tracking robustness and generalization across multiple tracking benchmarks.

Architecture
The GOT-JEPA architecture is divided into two main components:

GOT-JEPA Framework:
1. Historical frames and previous tracking results provide contextual information about the target.
2. A Teacher Predictor processes clean frames and generates pseudo tracking models.
3. A Student Predictor receives corrupted frames and learns to predict the teacher's tracking models.
4. The teacher-student JEPA objective improves robustness to appearance changes, distractors, and noisy observations.

OccuSolver:
5. OccuSolver performs fine-grained visibility estimation using point-based object tracking.
6. It models occlusion patterns and refines object visibility information.
7. The refined visibility cues are used to improve tracking performance under partial and full occlusions.


### Evaluation 
Shih-Fang et al. evaluated GOT-JEPA on seven generic object tracking benchmarks to measure tracking accuracy, robustness, generalization to unseen targets, and performance under adverse visibility conditions. The evaluation included challenging scenarios involving occlusions, distractors, deformation, and background clutter.

### Results
Shih-Fang et al. report that GOT-JEPA achieved a 63.7% success rate on AVisT, surpassing PiVOT (62.2%), and an average overlap of 79.6% on GOT-10k. The results demonstrate strong tracking accuracy, generalization, and robustness to occlusions.
