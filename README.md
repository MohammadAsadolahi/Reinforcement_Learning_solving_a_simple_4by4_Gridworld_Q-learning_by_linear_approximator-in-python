# Reinforcement_Learning_solving_a_simple_4by4_Gridworld_using_Q-learning_by_linear_approximator
Reinforcement Learning solving a simple 4*4_ Gridworld using Q-learning by linear approximator
  
WRITTEN BY MOHAMMAD ASADOLAHI  
Mohammad.E.Asadolahi@gmail.com  
https://github.com/mohammadAsadolahi  
**!!!! its not Deep Q-learning implementation!!! for Deep Q-learning version search my github repo**
![4*4 gridworld](https://github.com/MohammadAsadolahi/Reinforcement_Learning_solving_a_simple_4_4_Gridworld_using_SARSA-in-python/blob/main/a%20simple%204%20by%204%20Gridworld.png)
this program is using Reinfrocement learning to solve a 4*4 gridworld like frozen lake enviroment in open ai gym  
the method used is policy iteration whitch is one of fundamental manners of Dynamic Programing  

     | S | O | O | O |  
     | O | O | O | * |  
     | O | * | O | O |  
     | O | * | O | T |  

  
  S= start cell  
  O= normal cells  
  *= penalized cells  
  T= terminate cell  
  
our agent goal is to find policy to go from S(start) cell to T(goal) cell with maximum reward(or minimum negative reward)  
valid actions are storend in GridWorld actions array.  
positive and negative rewards in each cell is stored in Gridworld  "Rewards" dictionary and can be modified by user .the current rewards for *(hole) cells ant T(goal) cell has been set to:  
self.rewards = {(3, 3): 5, (1, 3): -2, (2, 1): -2, (3, 1): -2}  
for example reward to go in (3,3) in enviroment witch is the goal will be +5 so agent gets +5 reward whenever go to cell (3,3)  
the size of Gridworld can be changed in GridWorld calss by adding space actions  
***************************
Algorithm Flow
***************************
  first we initialize a random policy that indicate prefered moves in every cell:  
  
    | D |  | L |  | R |  | D | 
    ----------------------------
    | U |  | U |  | R |  | D | 
    ----------------------------
    | D |  | R |  | R |  | U | 
    ----------------------------
    | U |  | L |  | R | 
    ----------------------------
 
U = going up  
D = going down  
L = going left  
R = going right  
  
and we initialize Q table like:  

    (0, 0): {'D': 0, 'R': 0},
    (0, 1): {'L': 0, 'D': 0, 'R': 0},
    (0, 2): {'L': 0, 'D': 0, 'R': 0},
    (0, 3): {'L': 0, 'D': 0},
    (1, 0): {'U': 0, 'D': 0, 'R': 0},
    (1, 1): {'U': 0, 'L': 0, 'D': 0, 'R': 0},
    (1, 2): {'U': 0, 'L': 0, 'D': 0, 'R': 0},
    (1, 3): {'U': 0, 'L': 0, 'D': 0},
    (2, 0): {'U': 0, 'D': 0, 'R': 0},
    (2, 1): {'U': 0, 'L': 0, 'D': 0, 'R': 0},
    (2, 2): {'U': 0, 'L': 0, 'D': 0, 'R': 0},
    (2, 3): {'U': 0, 'L': 0, 'D': 0},
    (3, 0): {'U': 0, 'R': 0},
    (3, 1): {'U': 0, 'L': 0, 'R': 0},
    (3, 2): {'U': 0, 'L': 0, 'R': 0}}
     
    
    
    
