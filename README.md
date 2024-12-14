# RL  
Tetris Env(Params):  
Height x Hidth (20 blocks x 10 blocks)  
is_Terminated (Game over)  
height (Current stack height)  
holes (From the perspective of a column, if there's a block at height   
h, any empty cells located below this block are defined as holes.)  
observation (Current board)  
# Reward Functions  
# Tetris Agent Reward/Penalty Mechanisms

| **Reward/Penalty Mechanism**   | **Description**                                                                   | **Desired Agent Behavior**                                      |
|--------------------------------|-----------------------------------------------------------------------------------|----------------------------------------------------------------|
| **Height Reward/Penalty**      | Reward when the height is below half, small penalty when exceeding a certain height. | Place blocks mainly in the lower half and avoid stacking too high too early.  |
| **Hole Count Reward/Penalty**  | Reward for reducing holes, small penalty for increasing holes.                    | Optimize block placement to minimize holes, enabling easier line clears.      |
| **Total Height Increase Penalty** | Large penalty if height increases by more than 2 in one step; small reward for maintaining low height. | Encourage horizontal block placement to maintain stability and avoid rapid height increases. |
| **Survival Time Reward (Adjusted)** | Previously rewarded survival time but caused "cheating" behavior (e.g., spinning to slow down falling). | **(Improved)** Avoid reliance on survival time reward to prevent unnatural behavior.       |
| **Drop Reward**                | Reward for quickly placing blocks.                                              | Encourage efficient block placement and speed up learning.                   |
| **Flatness Reward/Penalty**    | Calculate the standard deviation of column heights; reward for flat surfaces, penalty for uneven or deep wells. | Learn to keep the board surface flat and avoid unstable structures or deep wells. |
| **Line Clear Reward**          | Reward for successfully clearing lines.                                        | Learn that clearing lines is the ultimate goal, reinforced by other rewards to achieve it. |

