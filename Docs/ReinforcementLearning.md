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


### Policy gradient methods with neural networks

Policy Gradient

Categorical Network MLP constructed with softmax output layer which gives probabilities over actions that sums up to 1. 
Backpropagate with cross-entropy multiclass log loss as starting gradient for gradient backpropagation.

cross entropy loss = - ground truth vector (labels) * LOG(output vector of categorical network)

ground truth vector (labels) = one hot encoded vector

In RL the one hot encoded is a fake label vector which consists of the chosen actions from the episodes. Then cross entropy is calculated for error gradient which is multiplied with advantage value for decreasing or increasing the likelihoods with respect to their advantage. 
Backpropagate this gradient for adjusting the weights and biases of the network. 

Exploration exploitation trade off - sampling from categorical distribution makes this automatically

Policy Gradient with baseline
Policy Gradient with rewards to go
    
### Actor critic methods (mix value learning with Policy gradient)

Value Function is learned with regression fitting
Policy Gradient Method is updated with the critic Value
g = critic_v * log(p)  

A3C rolls out multiple actors that act in different instances of the training environment and collect training samples. Policy function is updated asynchronous. Maybe the agents train on an older policy.
 
A2C - Synchronous version of A3C - Policy update is performed after all agents stopped collecting samples. The gradient is averages over all agents samples. So the agents always train on the same policy

PPO (Proximal Policy Optimzation)
Actor Critic with Clipping during gradient update to stay in a trust region for the policy update
Make use of GAE (General Advantage Estimate)

Us Entropy bonus for exploration

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
