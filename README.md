Autonomous Delivery Agent: A Pathfinding Simulation
This project is an autonomous delivery agent simulation on a 2D grid, implemented in Python and designed to run in a Google Colab environment. It serves as a practical demonstration and comparison of various artificial intelligence search algorithms in a realistic scenario.

Features
The simulation includes the following core components:

Environment Modeling: A 2D grid representing a city with static obstacles (impassable areas), varying terrain costs (e.g., roads vs. rough terrain), and dynamic moving obstacles.

Pathfinding Algorithms:

Uninformed Search (Uniform-Cost Search): A baseline algorithm that finds the optimal path based purely on cost, without directional guidance.

*Informed Search (A):** A powerful and efficient algorithm that uses an admissible heuristic (Manhattan Distance) to intelligently guide the search toward the goal, significantly reducing the number of nodes expanded.

Local Search Replanning (Simulated Annealing): A strategy for handling unexpected, real-time events. When the agent's pre-planned path is blocked by a new dynamic obstacle, this algorithm quickly finds a short-term detour to avoid a collision.

Experimental Comparison: The code runs experiments to compare the performance of Uniform-Cost Search and A* based on key metrics:

Path Cost: The total cost of the final route.

Nodes Expanded: A measure of the computational effort.

Execution Time: The time it takes for the algorithm to find a solution.

Visualization: The project includes matplotlib-based visualizations to show the grid, obstacles, expanded nodes, and the final path, providing clear insights into how each algorithm works.

How to Run
Open in Google Colab: Click the "Open in Colab" badge below to launch the notebook directly in your browser.

Run All Cells: Once the notebook is open, go to the top menu and click "Runtime" -> "Run all".

The notebook will execute each step sequentially, from installing dependencies to running the experiments and displaying the results and visualizations. You can also run the cells individually to see the output of each section.

Files
delivery_agent_simulation.ipynb: The main Google Colab notebook containing all the code, experiments, and analysis.

Analysis and Discussion
The notebook provides a detailed analysis of when each algorithm is most effective. In essence:

A* is the superior choice for static pathfinding due to its speed and efficiency.

A hybrid approach using A* for global planning and a local search method like Simulated Annealing for reactive replanning is ideal for dynamic environments.

Feel free to modify the grid size, obstacle density, and terrain costs in the code to test the algorithms under different conditions.
