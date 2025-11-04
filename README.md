# Multi-Agent A* Pathfinding Visualization

This Python project implements a visual simulation of multi-agent pathfinding using the **A\* search algorithm** and the **Tkinter** library for the graphical user interface. It demonstrates how two agents (Agent A and Agent B) can find their respective paths from a starting point to a goal on a grid, while considering obstacles and **avoiding each other's paths** (a simplified form of collision avoidance).

## ✨ Features

* **Interactive Grid:** A 10x10 grid where you can set obstacles, start points, and goal points.
* **Two Agents:** Supports two agents, Agent A (Green) and Agent B (Blue), each with a separate start and goal.
* **A\* Pathfinding:** Uses the classic A\* algorithm to find the shortest path.
* **Collision Avoidance:** Agents' paths are reserved sequentially, meaning one agent's calculated path becomes an "obstacle" for the next agent, preventing direct path overlap.
* **Visualization:** Highlights obstacles, visited nodes, and the final calculated path.
* **Animation:** Animates the agents moving along their calculated paths.

## 🚀 Getting Started

### Prerequisites

You need Python installed on your system. This project uses standard libraries, so no additional `pip` installation is required beyond what comes with a standard Python distribution.

* Python 3.x
* `tkinter` (usually bundled with Python)

### Running the Application

1.  Save the provided code as `pathfind.py`.
2.  Open your terminal or command prompt.
3.  Navigate to the directory where you saved the file.
4.  Run the script:

    ```bash
    python pathfind.py
    ```

## 🎮 How to Use

The application window contains the grid and control buttons.

### 1. Setting Up the Map

By default, the application starts in **"Placing Obstacles"** mode.

* **Placing Obstacles:** Click any cell on the grid to toggle it as an obstacle (black). Click the button labeled "Placing Obstacles" to switch modes.
* **Setting Start/Goal:**
    1.  Click the **"Placing Obstacles"** button to switch to **"Setting Start/Goal"** mode.
    2.  Use the **"Active Agent: A/B"** button to choose which agent you are setting points for.
    3.  For the **active agent**, the first click sets the **Start** point (agent color), and the second click sets the **Goal** point (red).
    4.  A third click will reset the Start point and clear the Goal.
    5.  Repeat this process for Agent A and Agent B until both have a valid Start and Goal.

### 2. Finding the Path

* Once both Agent A and Agent B have their Start and Goal points set, click the **"Start Multi-Agent A\*"** button.
* The visualization will first show the **paths** and **visited nodes** found by the A\* algorithm.
* The system then **animates** both agents moving simultaneously along their respective paths.

## 🧠 Technical Details

The core pathfinding logic is implemented in the `astar` function.

* **Heuristic:** Uses the **Manhattan distance** (taxicab distance).
* **Collision Handling (Simplified):** The `visualize_multi_agent` function handles the multi-agent logic. It runs A\* for Agent A first. Then, it adds **Agent A's entire path** to the `occupied` set, which acts as a dynamic obstacle for the subsequent search of Agent B. This ensures the agents use completely separate paths.
* **Visualization:** The `draw_grid` function uses Tkinter's canvas to render the grid, paths, visited nodes, and agent locations.

## 🤝 Contributing

Feel free to fork the repository and submit pull requests with improvements, such as more advanced collision resolution (e.g., time-based reservations) or additional features!
