# Reinforcement Learning Approach for Settlers of Catan

This project explores reinforcement learning strategies for playing the strategic board game **Settlers of Catan**. Given the game's complexity, including a large state and action space, we evaluate different agent strategies, including **Monte Carlo Tree Search (MCTS), greedy agents, and a random agent**.

## Overview

Settlers of Catan is a resource-management and strategy game where players compete to earn **10 victory points** by building settlements, cities, roads, and acquiring special achievements. Players must **manage resources, make strategic trades, and plan their expansions** while interacting with a dynamic environment.

### Project Goals
- Implement **Monte Carlo Tree Search (MCTS)** for decision-making.
- Compare MCTS with **greedy agents** (one prioritizing building, another focusing on development cards) and a **random agent**.
- Evaluate agent performance based on **victory points** across multiple simulated games.
- Investigate **transfer learning** by training on one board setup and testing on a different random configuration.

## Related Work

This project builds on previous research in reinforcement learning for board games, including:
- **Deep Reinforcement Learning in Strategic Board Game Environments** by Konstantia Xenou et al.
- **Playing Catan with Cross-Dimensional Neural Networks** by Quentin Gendre and Tomoyuki Kaneko.
- **Introduction to Monte Carlo Tree Search** by Jeff Bradberry.

These works helped shape our approach, from **structuring the board representation** to implementing **MCTS for decision-making**.

## Implementation Details

### Game Environment
- **Hexagonal grid representation** with randomized resource tile assignments.
- **Player actions** include building, upgrading, trading at ports, and buying development cards.
- **Victory points** serve as the **reward function** for reinforcement learning.

### Agents
1. **Monte Carlo Tree Search (MCTS)**  
   - Uses **Upper Confidence Bound (UCB1)** for exploration/exploitation.
   - Learns from simulations and backpropagates victory points.
   
2. **Greedy Building Agent**  
   - Prioritizes **building cities > settlements > roads** to maximize points.
   
3. **Greedy Development Agent**  
   - Focuses on **development cards** and **port trades** to gain an advantage.
   
4. **Random Agent**  
   - Selects actions randomly, serving as a baseline for comparison.

## Evaluation

### Experiment Setup
- **100 simulated games** with a maximum of **100 moves per game**.
- Each player was allowed up to **5 moves per turn**.
- Agents started with **predefined settlement placements** and an initial set of resources.

### Results
- **Early-game performance:** The **greedy-building agent** outperformed others initially.
- **Long-term performance:** The **MCTS agent improved over time**, surpassing the greedy-building agent.
- **Greedy-development and random agents** performed worse overall.

## Challenges and Future Work

### Challenges
- **Large state space:** The complexity of Catan made **MCTS learning slow**.
- **Limited trading mechanics:** The current version does not support **player-to-player trading**, an important part of the game.
- **No human comparison:** Agents were compared to each other but not against human players.

### Future Work
- **Visualization & GUI**: Implement a game visualization to **observe agent behavior**.
- **Improved agents**: Explore **neural networks, Q-learning, or deep reinforcement learning**.
- **Player trading**: Implement **agent negotiation** for resource trades.
- **Human-AI gameplay**: Allow a human player to compete against the AI agents.

## References
1. Konstantia Xenou, Georgios Chalkiadakis, and Stergos Afantenos. *Deep Reinforcement Learning in Strategic Board Game Environments* (2019).
2. Quentin Gendre, Tomoyuki Kaneko. *Playing Catan with Cross-Dimensional Neural Network* (2020).
3. Jeff Bradberry. *Introduction to Monte Carlo Tree Search* (2015).

