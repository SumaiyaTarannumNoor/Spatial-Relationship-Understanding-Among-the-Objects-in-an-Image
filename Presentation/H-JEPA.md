## A path Towards Autonomous Machine Intelligence Version 0.9.2
-- https://www.youtube.com/watch?v=NLSm51ba--k&t=8

The author states in the prologue section that this piece is neither a scholarly paper nor a technical paper, but a position paper to express their vision.

In this position paper, the author proposes an architecture and training paradigm with which to construct autonomous intelligent agents. It combines concepts such as a configurable predictive world model, behaviour driven through intrinsic motivation, and hierarchical joint embedding architectures trained with self-supervised learning. 

The main contributions of this paper are:
1. An overall cognitive architecture in which all modules are differentiable and many of them are trainable.
2. JEPA and Hierarchical JEPA: a non-generative architecture for predictive world models that learn a hierarchy of representations.
3. A non-contrasive self-supervised learning paradigm that produces representations that are simultaneously informative and predictable.
4. A way to use H-JEPA as the basis of predictive world models for hierarchical planning under uncertainty. 

The H-Jepa architecture consists of 5 differentiable modules:
1. World Model: The central component that predicts future states of the world based on the current state and intended actions. It uses a hierarchy of Joint-Embedding Predictive Architectures (JEPAs).
2. Perception Module: Acts as an encoder to process raw sensory data (like video or audio) from the environment into useful representations for the rest of the modules.
3. Actor:  Responsible for generating action plans to accomplish current tasks. It functions at multiple levels of abstraction to convert high-level goals into concrete motor controls.
4. Critic Module: Evaluates the predicted outcomes of planned actions, helping the agent find the optimal path under uncertainty.
5. Configurator: A meta-controller or gating mechanism that dynamically adjusts the settings of all other modules based on the specific current task.
