## Semantic World Model
World Models are a type of model capable of predicting the future given a large amount of data. 
A generalized world model that is represented as an action-cobditional vision-language model that answers questions about the semantic effects of actions in the future.
These types of models utilise Multimodal Data, which leads to the
question, "What is multimodal data"? 
Multimodal data is a combination of different types of data, such as text, images, audio, video, and sensor readings, that are combined and used in a single system to complete complex tasks, such as predicting the next action.
In this paper titled, **Semantic World Models**, Jacob et al. introduce a generalized world model that is represented as an action-conditional vision-language model that answers questions about frames, more accurately future frames given the current observations and a sequence of actions.
SWM was evaluated on a set of multiple different tasks in twoi commonly used multi-task simulation domains - Language Table (LangTable) and OGBench.
These evaluations show two observations:
1. SWM can accurately answer questions about future outcomes while generalizing to novel scenes, and
2. SWM can be combined with standard sampling-based planning techniques and a gradient-based improvement technique to solve diverse robotic tasks with considerable policy improvement through test-time optimization.

### Dataset
To train this SWM, Jacob et al. generated a SAQA dataset, which is a state-action-question-answer dataset.
D<sub>SAQA</sub> = {(S<sub>i</sub>,a<sub>i:j</sub>,Q<sub>S<sub>j</sub></sub>, A<sub>S<sub>j</sub></sub>)....} where j = i + h

Here, <br>
S<sub>i</sub> = Current state (RGB frame in our case) <br>
h = horizon <br>
a<sub>i:j</sub> = Sequence of actions taken from state S<sub>i</sub> <br>
Q<sub>S<sub>j</sub></sub>, A<sub>S<sub>j</sub></sub> = question answer tuple about future state S<sub>j</sub> which is reached by taking actions a<sub>i:j</sub> from state S<sub>i</sub>

* **Horizon ($h$):** The total number of time steps (clock ticks) to get from the starting state $S_i$ to the future state $S_j$.
* **Action Sequence ($a_{i:j}$):** The ordered list of actions the agent takes during those $h$ steps to bridge the gap.

### Architecture
The SWM architecture is based on an open-source VLM (Video Language Model) named PaliGemma.
SWM contains three core pretrained components:
1. A transformer-based autoregressive language model with token embedding size d<sub>tok</sub>
2. A vision encoder υ<sub>Φ</sub> with a feature size d<sub>img</sub> and,
3. A projection matrix W ∈ R <sup>d<sub>tok</sub> x d<sub>img</sub></sup>

This paper uses a 3B parameter checkpoint from PaliGemma as the base model.

To adapt the base model (PaliGemma 3B Parameter Checkpoint) to answer questions about a specific future as a result of the actions, the model needs to be conditioned on the actions.

In a semantic world model, planning is a live decision-making process using high-level concepts. Here, they used two types of planning - Sampling-based planning, which requires a large number of samples and gradient-based planning with a base proposal policy. The gradient can provide directed information for optimizing the model for faster convergence. Another planning was used for Multistep tasks, with the idea that SWM can be used to track task progress and transition between subgoals without requiring any additional components.

### Results
SWM demonstrates an average performance increase over the base policies from 14.4% to 81.6% on average for lang table and 45.33% to 76% on average for OFBench. SWM also outperforms both AVD (Action Conditioned Video Diffusion) and IDQL (Implicit Diffusion Q-Learning) baselines across all tasks, demonstrating the effectiveness of SWM for planning.




