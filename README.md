
# Maze RL — Visual Exploration & Final Path (Q-Learning)

This project is an interactive web-based visualization of Q-Learning in a maze environment. Users can design mazes, train an agent using Q-Learning, and see the final optimal path after training.

---

## Features

- **Interactive Maze Editor**
  - Left-click to toggle walls.
  - Shift + left-click to set the goal (treasure).
  - Right-click to set the start (agent position).

- **Q-Learning Parameters**
  - `α` (alpha): Learning rate.
  - `γ` (gamma): Discount factor.
  - `ε` (epsilon): Exploration rate.
  - Adjustable number of training episodes.

- **Training & Visualization**
  - Start, pause, step, or stop training.
  - Animated agent movement during training.
  - Visit heatmap showing how often each cell has been visited.
  - Display final greedy path after training.
  
- **Q-Table Management**
  - Copy and paste Q-table JSON.
  - Reset Q-table to start fresh training.

---

## How to Use

1. **Set up the Maze**
   - Click to add walls.
   - Shift + Click to set a goal.
   - Right-click to set the start position.

2. **Adjust Parameters**
   - Set grid size, cell size, and Q-Learning parameters (α, γ, ε).
   - Set the number of episodes for training.

3. **Train the Agent**
   - Click **Start Train** to begin training.
   - Pause or step through episodes using the respective buttons.

4. **Visualize Results**
   - The agent’s path will be animated in blue.
   - After training, click **Show Final Path** to overlay the optimal path.
   - Red overlay indicates visited cells (heatmap).

5. **Q-Table Management**
   - **Copy Q**: Copies the current Q-table to clipboard.
   - **Paste Q**: Loads a Q-table from clipboard.
   - **Reset Q**: Clears the learned Q-table and visitation counts.

---

## Controls Summary

| Action | Interaction |
|--------|------------|
| Toggle wall | Left-click |
| Set goal | Shift + Left-click |
| Set start | Right-click |
| Start/Stop Training | Button: Start Train |
| Pause/Resume Training | Button: Pause |
| Step Episode | Button: Step Ep |
| Reset Q-Table | Button: Reset Q |
| Show Final Path | Button: Show Final Path |
| Copy Q-Table | Button: Copy Q |
| Paste Q-Table | Button: Paste Q |

**Keyboard Shortcuts**
- `Space`: Pause/Resume training
- `r`: Reset Q-table
- `p`: Show final path

---

## Q-Learning Details

- **State:** Each cell `(row, column)` in the grid.
- **Actions:** Up, Right, Down, Left.
- **Reward Function:**
  - `-0.04` for regular move
  - `-0.6` for hitting a wall
  - `10` for reaching the goal
- **Update Rule:**
  - `Q(s,a) = Q(s,a) + α * (reward + γ * max(Q(s', all_actions)) - Q(s,a))`

- **Policy:** Epsilon-greedy:
- With probability ε, choose a random action.
- With probability 1-ε, choose the best action from Q-table.

---