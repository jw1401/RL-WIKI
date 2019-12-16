## Math

- Statistics and Probability theory, 
- calculus
- algebra

## Markov Decision Process
- Framework for RL

## RL terminology

- Value learning
- Value, Q(s,a), Advantage
- Bellman equation
- Monte-Carlo vs Temporal Difference methods
- Exploration-Exploitation trade-off

## RL Algorithms

### Q-Learning, Value based, tabular approach

- DQN Q-Learning tabular or with Deep Neural Networks

- DQN advances - Target network, Double Q, Duelling Q, Prioritized experience replay

In Deep Q learning a value function is learned via Regression (Function fitting) with MSE via the Bellman equation

This can be done Monte Carlo or TD style or mixed via TD Lambda and the GAE 

Search can be done greedily - always chose ARGMAX(Value)

Exploration exploitation - epsilon greedy trade off
  
- always goes to the global optimum
- just for discrete action spaces
- has high variance

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
