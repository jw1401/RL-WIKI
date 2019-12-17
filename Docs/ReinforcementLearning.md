# Reinforcement Learning

Reinforcement learning is the training of machine learning models to make a sequence of decisions based on observations. The agent learns to achieve a goal in an uncertain, potentially complex environment. The agent employs trial and error to come up with a solution to the problem. To get the machine to do what the programmer wants, the artificial intelligence gets either rewards or penalties for the actions it performs. Its goal is to maximize the total reward.


## Useful thigs to know

- Statistics and Probability-Theory, 
- Calculus
- Algebra
- Markov Decision Process


## RL Terminology

- Value based RL with V(s), Q(s,a), Advantage
- Bellman equation
- Monte-Carlo vs Temporal Difference methods
- Exploration-Exploitation trade-off


## RL Algorithms

### Q-Learning

Q-Learning is a value based approach where the agent takes actions where the biggest Values/Advantages (based on Rewards) can be achieved. It is suitable for Discrete action spaces and can be performed in a Tabular style or with Deep Learning.

Q-Learning 

- Tabular approach

  Generates a Table where a an agent can choose the most valuable Action based on its state via the Q-Value
     
- Deep Neural Networks --> Deep Q Learning (DQN)

  States are feed to a Neural Networ that outputs Q-Values for actions. The NN is learning the Q-Values by interacting with the       Environment. For Eyploitation/ Exploration a Epsilon Greedy Trade Off is used. Greedily means- always chose the most valuable Value (ARGMAX of Value). Exploration means to use random actions. Q-Learning always goes to the global optimum but has a high variance.

DQN Advances 

- Target Networks
- Double Q Learning 
- Duelling Q Networks
- Prioritized Experience Replay
- Noisy Networks for Exploration


### Policy Gradient Methods with Deep Learning

## Policy Gradient

The Policy Gradient Method directly maps States to Actions with the goal to maximize rewards.

### Working under the hood for Discrete Actions

Steps:
 
  - Feed Forward a Categorical Network (uses Softmax output which gives probabilities over actions that sums up to 1) to get actions.
  - Interact with the Environment a receive Rewards or Punishment
  - Calculate Rewards to go or with Baselines
  - Use Cross-Entropy Method and Rewards for gradient backpropagation. 
  
  ```
  Cross Entropy Loss = - LOG(Policy) * Ground-Truth-Vector (Labels) ... Labels = One Hot Vector
  Policy Loss = Cross Entropy Loss * Rewards
  ```

The one hot encoded can be interpreted as a fake label which consists of the choosen actions from the episode. Then Cross Entropy is computed for gradients. Gradients are multiplied with Advantage or Reward Values for decreasing or increasing the likelihood of action probabilities with respect to their Advantage. Ultimately backpropagate this gradient for adjusting the weights and biases of the NN. By sampling from a Categorical Distribution the Exploration Exploitation trade off is handled automatically.

    
### Actor-Critic Methods 

Actor-Critic combines Value Learning with Policy Gradient methods. The Critic tells the Actor how good the choosen action was and updates it accordingly.

- Critic

  Value Function is the critic and is learned with Regression methods

- Actor

  Policy Gradient is the actor which is updated with the critics values

```
  Policy Loss = - LOG(Policy) * Critic(Values)  
```

After a lot of interaction steps useful policies can be learned. Following advancements achive better results.

- A3C 

  Rolls out multiple actors that act in different environments and collect training samples. Policy function is updated asynchronous. 
 
- A2C 

  Synchronous version of A3C - Policy update is performed after all agents stopped collecting samples. The gradient averages over all agents samples. The agents always act on the same policy

- PPO (Proximal Policy Optimzation)

  Actor-Critic method that clips gradients during the update steps to stay in a trust region of the Policy and not move to far away from the old Policy. 
  

- Make use of General Advantage Estimation (GAE) which mixes Monte Carlo with Temporal Difference Learning

- Give the Policy an Entropy Bonus for better exploration

### Soft Actor Critic

- Max Entropy RL Method
- Like Q Learning for Continuous Acion Spaces 

### RL Algorithm categories

- Model-free
- Model-based 
- On-policy
- Off-policy

### MISC

- Baseline algorithms (OpenAI, Uber, Berkley)

- Reward engineering
- Sparse reward problem
- Dense rewards
- Curiosity driven learning - intrinsic rewards

- Inverse RL (learning a reward function)

- Multiagent environment
- Concurrent agent learning
- Multiple agents

- Meta learning
- Learn to learn

- Hierarchy learning
- Make subtask policies and master policy

### Imitation learning, behavioral cloning (VR, AR)

Learning by showing samples to the agent by experts

- Curriculum learning
Learning from easy to hard tasks

- Metrics
Performance measuring
Generalization abilities of agent

- AI Safety
Understand what the trained agent is doing and can you trust him
Agent visualisation 
Agent testing
Agent NOT HALT
