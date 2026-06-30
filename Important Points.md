## VQA - Visual Question-Answering
## VLM - Vision Language Model

## Semantic World Model (SWM)
A generalized world model that is represented as an action-cobditional vision-language model that answers questions about the semantic effects of actions in the future.

## VLM
Vision Language Model, this answers the questions about the object that can be seen in the image, for ezample - What is the colour of the flower? It's about static observation.

## VWM 
Video World Model, this predicts the future observation about the object that can be seen. For example - Will the ball move? It's about action sequence prediction.

## SWM
Semantic World Model, is a combination of both VLM and VWM. It takes both object observations and then predicts the future action sequence about them. For example - Will the Blue ball touch the red ball?

Traditional world model predicts future frames. But, Semantic World Model answers questions about the future given current observations (represented as an image) and a sequence of actions.

## Task-agnostic
Task-agnostic means operating independently of specific tasks or objectives. It describes systems, algorithms, or methods that function generally without requiring prior knowledge of, or adjustments for, the specific job.
It describes a model that can solve many different types of problems without changing it's core structure. It's about model flexibility.
