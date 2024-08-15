# 📊 Unsupervised Learning: K-Means Clustering and PCA

## K-Means Clustering

### Overview
K-Means clustering is an algorithm used to partition a dataset into \(k\) clusters, where each point belongs to the cluster with the nearest centroid. The goal is to minimize the variance within each cluster.

### Key Concepts
1. **Centroid Initialization**:
   - **Random Initialization**: Centroids are initialized randomly. If a cluster ends up with zero points, it can either be eliminated or its centroid reinitialized randomly. 🔄

2. **Objective Function**:
   - K-Means minimizes the **distortion**, which is the squared distance between points and their corresponding centroids. 📉

3. **Algorithm Steps**:
   - **Assignment Step**: Assign each point to the nearest centroid. 📍
   - **Update Step**: Recalculate centroids as the mean of all points assigned to each cluster. 📊
   - **Repeat**: Iterate the above steps until convergence. 🔁

4. **Finding Optimal \(k\)**:
   - Run the algorithm multiple times with different \(k\) values to find the best local optimum. 🔍
   - **Elbow Method**: Plot the sum of squared distances from points to their centroids versus \(k\) and look for an "elbow" where the rate of decrease slows down. (Note: Not always recommended due to subjectivity.) 📉🦵

## PCA (Principal Component Analysis)

### Overview
PCA is a technique for dimensionality reduction while preserving as much variance as possible. It is used for visualization and feature reduction.

### Key Concepts
1. **Principal Components**:
   - PCA finds new axes (principal components) that maximize the variance of the data. 📈
   - Each principal component is orthogonal to the others (90 degrees apart). 🔲

2. **Transformation**:
   - **Mean Normalization**: Subtract the mean of each feature. 🌟
   - **Fit and Transform**: Use `fit` to determine the principal components and `transform` to project data onto these new axes. 🔄

3. **Explained Variance**:
   - Use `explained_variance_ratio_` to determine how much variance is captured by each principal component. 📊

4. **Applications**:
   - PCA is used for visualization and data compression but is less common now due to advances in storage and transfer rates. 🚀

# 🤖 Reinforcement Learning

## Overview
Reinforcement Learning (RL) is a learning paradigm where an agent learns to make decisions by receiving rewards or penalties based on its actions in different states.

## Key Concepts
1. **State, Action, Reward**:
   - **State (s)**: Current situation of the agent. 🌍
   - **Action (a)**: Decision or move the agent makes. 🚀
   - **Reward (R)**: Feedback received after taking action. 🏅

2. **Return**:
   - **Return**: The sum of rewards, discounted by a factor \(\gamma \), over time. ⏳
   - **Formula**: \( \text{Return} = R_1 + \gamma R_2 + \gamma^2 R_3 + \ldots + \gamma^{n-1} R_n \)
   - **Discount Factor (\(\gamma\))**: A value between 0 and 1 that determines the importance of future rewards. Lower \(\gamma\) makes the agent more impatient. ⏱️

3. **Policy (\(\pi\))**:
   - A policy maps states to actions, aiming to maximize the return. 📈

4. **Markov Decision Process (MDP)**:
   - The future depends only on the current state, not on the history of previous states. 🕒

5. **Q-Learning**:
   - **Q-Value**: Represents the return expected from taking action \(a\) in state \(s\) and behaving optimally thereafter. 🎯
   - **Bellman Equation**:
     \[
     Q(s, a) = R(s) + \gamma \max_{a'} Q(s', a')
     \]
   - In terminal states, \( Q(s, a) = R(s) \). 🏁

6. **Stochastic Environment**:
   - Expected Return is used to account for randomness in the environment:
     \[
     Q(s, a) = R(s) + \gamma \mathbb{E}[\max_{a'} Q(s', a')]
     \]
   - Average (Expectation) operator accounts for possible variations in the state \(s'\). 🌐

7. **Deep Q-Learning (DQN)**:
   - Uses neural networks to approximate Q-values. 🧠
   - Uses techniques such as experience replay and epsilon-greedy policies to improve learning efficiency. 🔄

8. **Epsilon-Greedy Policy**:
   - With probability \(\epsilon \), choose a random action (exploration); otherwise, choose the action with the highest Q-value (exploitation). 🔍
   - Epsilon decreases over time to balance exploration and exploitation. 📉

9. **Mini-Batch and Soft Updates**:
   - **Mini-Batch**: Speed up training by using subsets of data for each iteration. ⚡
   - **Soft Update**: Smooths the update of Q-values to prevent abrupt changes:
     \[
     W_{\text{new}} = \alpha W_{\text{old}} + (1 - \alpha) W
     \]
     where \(\alpha \) is a small hyperparameter. 🌟

## Limitations
- Reinforcement learning is often easier to apply in simulated environments compared to real-world scenarios. Applications are relatively fewer. 🌐

## Tools
- **OpenAI Gym**: A toolkit for developing and comparing RL algorithms. 🏋️‍♂️
