# AIML-Kanjul-Verma

Autonomous Delivery Agent: A Pathfinding Simulation
This project is an autonomous delivery agent simulation on a 2D grid, implemented in Python and designed to run in a Google Colab environment. It serves as a practical demonstration and comparison of various artificial intelligence search algorithms in a realistic scenario.

Features
The simulation includes the following core components:

Environment Modeling: A 2D grid representing a city with static obstacles (impassable areas), varying terrain costs (e.g., roads vs. rough terrain), and dynamic moving obstacles.

Pathfinding Algorithms:

Uninformed Search (Uniform-Cost Search): A baseline algorithm that finds the optimal path based purely on cost, without directional guidance.

Informed Search (A):* A powerful and efficient algorithm that uses an admissible heuristic (Manhattan Distance) to intelligently guide the search toward the goal, significantly reducing the number of nodes expanded.

Local Search Replanning (Simulated Annealing): A strategy for handling unexpected, real-time events. When the agent's pre-planned path is blocked by a new dynamic obstacle, this algorithm quickly finds a short-term detour to avoid a collision.

Experimental Comparison: The code runs experiments to compare the performance of Uniform-Cost Search and A* based on key metrics:

Path Cost: The total cost of the final route.

Nodes Expanded: A measure of the computational effort.

Execution Time: The time it takes for the algorithm to find a solution.

Visualization: The project includes matplotlib-based visualizations to show the grid, obstacles, expanded nodes, and the final path, providing clear insights into how each algorithm works.

How to Run
Open in Google Colab: Click the "Open in Colab" badge below to launch the notebook directly in your browser.
