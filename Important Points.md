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

D<sub>SAQA</sub> = {(S<sub>i</sub>,a<sub>i:j</sub>,Q<sub>S</sub><sub>j</sub>, A<sub>S</sub><sub>j</sub>)....} where j = i + h



## Task-agnostic
Task-agnostic means operating independently of specific tasks or objectives. It describes systems, algorithms, or methods that function generally without requiring prior knowledge of, or adjustments for, the specific job.
It describes a model that can solve many different types of problems without changing it's core structure. It's about model flexibility.
