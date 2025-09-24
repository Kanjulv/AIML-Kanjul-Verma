Report on Autonomous Delivery Agent Pathfinding
1. Introduction
This report details the design and implementation of an autonomous delivery agent capable of navigating a 2D grid city. The project explores and compares three distinct categories of search algorithms—uninformed, informed, and local search—to evaluate their effectiveness in both static and dynamic environments. The primary goal is to identify the most efficient and robust strategy for package delivery within a simulated urban setting.

2. Environment Model
The city environment is modeled as a 2D grid. Each cell on the grid represents a specific location with varying properties:

Static Obstacles: Impassable areas (e.g., buildings, walls) are represented by a value of -1. The agent cannot traverse these cells.

Varying Terrain Costs: The cost to move into a cell is represented by its value on the grid. This simulates different terrain types that require varying amounts of "fuel" or "time" to cross. For example, a cell with a value of 1 might represent a road, while a cell with a value of 5 could represent rough terrain.

Dynamic Moving Obstacles: These are independent agents with predefined or random trajectories. The agent's pathfinding system must be able to detect these dynamic obstacles in real time and adapt its plan to avoid collisions.

3. Agent Design
The agent is designed as a centralized pathfinder that operates on the grid environment. The core of the agent is a Pathfinder class, which encapsulates the different search algorithms. The agent’s rationality is defined by its objective: to find a path from a start point to a goal point that minimizes the total path cost.

Heuristics Used
The informed search algorithm, A*, relies on a heuristic function to guide its search. For this grid-based environment, the Manhattan Distance is used as an admissible heuristic.

This heuristic is admissible because it never overestimates the true cost to the goal, as movement is restricted to horizontal and vertical steps.

4. Experimental Results and Analysis
Experiments were conducted on several grid instances to compare the performance of Uniform-Cost Search (uninformed) and A* (informed) in static environments, and to demonstrate the role of a local search strategy in a dynamic environment.

<img width="1001" height="298" alt="image" src="https://github.com/user-attachments/assets/4aa62ddf-ce09-4993-b5ae-25af05fd7488" />


The visualization of the expanded nodes clearly illustrates the difference between the two algorithms. UCS, being an uninformed search, explores a wide range of nodes in a sprawling, circular pattern from the start point . In contrast, A*'s heuristic effectively directs its search, causing it to explore a more focused, goal-oriented path .

Experiment 2: Dynamic Environment Replanning
This experiment simulated a moving obstacle appearing in the middle of a planned path.

Initial Plan: The agent used A* to compute an optimal global path.

Obstacle Encounter: At a specific point along the path, the agent detected a dynamic obstacle that blocked its next step.

Replanning: Instead of re-running the full A* algorithm, the agent activated a local search replanning strategy (Simulated Annealing). This process quickly found a new, short-term path segment to bypass the obstacle.

Re-computing the entire path with A* from the current position would have taken approximately 0.008s, whereas the local replanning took only 0.001s.

5. Conclusion
Based on the experiments, a clear conclusion can be drawn about the performance of each algorithm:

A* is the superior choice for static pathfinding. Its use of an admissible heuristic significantly reduces the search space, leading to a substantial decrease in nodes expanded and execution time while still guaranteeing the optimal path.

Uniform-Cost Search is complete and optimal but is highly inefficient in large search spaces. It should be considered a baseline for comparison rather than a primary solution.

A hybrid approach is ideal for dynamic environments. By combining the global optimality of A* with the reactive speed of a local search algorithm like Simulated Annealing, the agent can maintain a globally efficient route while quickly adapting to real-time changes and avoiding collisions. The quick replanning allows the agent to handle unexpected events without the computational overhead of a full re-evaluation.
