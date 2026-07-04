# SAQA Dataset Instances Sample (Horizon h = 3)

This file contains sample instances for the State-Action-Question-Answer ($D_{SAQA}$) dataset. 
In these instances, the horizon is set to **h = 3**, meaning the target state $j$ is always 3 time-steps ahead of the starting state $i$ ($j = i + 3$).

---

## Instance 1: Autonomous Driving Scene

* **Current State ($S_i$):** `images/scene_001_frame_0.png` (Showing a car in the middle lane, 50 meters behind a red truck)
* **Horizon ($h$):** 3
* **Action Sequence ($a_{i:j}$):**
  1. `STEP 0`: "Accelerate"
  2. `STEP 1`: "Change lane left"
  3. `STEP 2`: "Maintain speed"
* **Target State ($S_j$):** *Reached at step 3 (not explicitly saved in the SAQA tuple, but used to generate the QA)*
* **Question ($Q_{S_j}$):** "Is the red truck now in front of our vehicle, or to our right?"
* **Answer ($A_{S_j}$):** "The red truck is to our right."

---

## Instance 2: Robotic Arm Assembly

* **Current State ($S_i$):** `images/scene_002_frame_12.png` (Showing a robotic gripper hovered over a table with a red cube and a blue bowl)
* **Horizon ($h$):** 3
* **Action Sequence ($a_{i:j}$):**
  1. `STEP 12`: "Lower gripper 10cm"
  2. `STEP 13`: "Close gripper fingers"
  3. `STEP 14`: "Lift gripper 10cm"
* **Target State ($S_j$):** *Reached at step 15*
* **Question ($Q_{S_j}$):** "What object is currently lifted off the table surface?"
* **Answer ($A_{S_j}$):** "The red cube."

---

## Instance 3: Video Game Agent (E.g., Pac-Man / Maze)

* **Current State ($S_i$):** `images/scene_003_frame_85.png` (Showing the player icon at an intersection, with a ghost located 2 tiles to the north)
* **Horizon ($h$):** 3
* **Action Sequence ($a_{i:j}$):**
  1. `STEP 85`: "Move South"
  2. `STEP 86`: "Move South"
  3. `STEP 87`: "Move East"
* **Target State ($S_j$):** *Reached at step 88*
* **Question ($Q_{S_j}$):** "Did the player collide with a ghost during or at the end of this sequence?"
* **Answer ($A_{S_j}$):** "No."
