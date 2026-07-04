## VQA - Visual Question-Answering
## VLM - Vision Language Model
## VLA - Vision Language Action

## Semantic World Model (SWM)
A generalized world model that is represented as an action-cobditional vision-language model that answers questions about the semantic effects of actions in the future.

## VLM
Vision Language Model, this answers the questions about the object that can be seen in the image, for ezample - What is the colour of the flower? It's about static observation.

## VWM 
Video World Model, this predicts the future observation about the object that can be seen. For example - Will the ball move? It's about action sequence prediction.

## VLA
VLAs are trained on annoted obot trajectories to generate actions conditioned on image observations and a language instruction.

## SWM
Semantic World Model, is a combination of both VLM and VWM. It takes both object observations and then predicts the future action sequence about them. For example - Will the Blue ball touch the red ball?

Traditional world model predicts future frames. But, Semantic World Model answers questions about the future given current observations (represented as an image) and a sequence of actions.

SWM is empirically evaluated on a set of multiple different tasks in two commonly used multi-task simulation domains - Language Table (Lang Table) and OGBench. This evaluation shows that (1) SWM can accurately answer questions about future outcomes while generalizing to novel scenes, and (2) SWM can be combined with standard sampling-bases planning techniques and a gradient-based improvement technique to solve diverse robotic tasks with considerable policy improvements through test-time optimization. SWM introduces a new class of world models that leverage the rich pretraining knowledge from VLMsfor grounded, flexible, and scalsble robotic control.

Unlike VLAs, an SWM takes in observations, actions, and a natural language prompt as input, and generates a natural language response about the future after taking the actions. 
In some sense, an SWM can be viewed as an "inverted" VLA, where the actions become the input and the language becomes the output. This approach hypothesizes that using language as the output format can better retain the pretraining knowledge of VLMs, since they were trained with next token prediction objectives.

world models for control are approximate models of the dynamics of the world, typically trained to predict future observations conditioned on current observations and actions. the ability to forcast the future without interacting with the world can greatly facilitate decision-making and control.


Unlike these explicit world models,SWM understands the dynamics of the world by reasoning in language space, allowing the model bootstrap from the Internet-scale pretraining of VLMs. SWM can then be used with planning techniques to derive versatile language-conditioned policies.

To train a world model to answer questions about the future, a state-action-question-answer (SAQA) dataset is generated 

D<sub>SAQA</sub> = {(S<sub>i</sub>,a<sub>i:j</sub>,Q<sub>S<sub>j</sub></sub>, A<sub>S<sub>j</sub></sub>)....} where j = i + h

Here, <br>
S<sub>i</sub> = Current state (RGB frame in our case) <br>
h = horizon <br>
a<sub>i:j</sub> = Sequence of actions taken from state S<sub>i</sub> <br>
Q<sub>S<sub>j</sub></sub>, A<sub>S<sub>j</sub></sub> = question answer tuple about future state S<sub>j</sub> which is reached by taking actions a<sub>i:j</sub> from state S<sub>i</sub>

* **Horizon ($h$):** The total number of time steps (clock ticks) to get from the starting state $S_i$ to the future state $S_j$.
* **Action Sequence ($a_{i:j}$):** The ordered list of actions the agent takes during those $h$ steps to bridge the gap.

### The Math Check
The formula states: 
$$j = i + h$$

If you start at step $i = 10$ and your horizon is $h = 3$, you will land at step $j = 13$.

Your action sequence $a_{i:j}$ will contain exactly 3 actions:
1. Action taken at step 10
2. Action taken at step 11
3. Action taken at step 12

### Architecture 
This SWM model is based on open-source VLM, PaliGemma.<br>
The model contains three core pre-trained components:
1. A transformer-based autoregressive language model with token embedding size d<sub>tok</sub> <br>
2. A vision encoder υ<sub>Φ</sub> with a feature size d<sub>img</sub> and,
3. A projection matrix W ∈ R <sup>d<sub>tok</sub> x d<sub>img</sub></sup>


## Task-agnostic
Task-agnostic means operating independently of specific tasks or objectives. It describes systems, algorithms, or methods that function generally without requiring prior knowledge of, or adjustments for, the specific job.
It describes a model that can solve many different types of problems without changing it's core structure. It's about model flexibility.
