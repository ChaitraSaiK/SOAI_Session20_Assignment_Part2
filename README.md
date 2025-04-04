# Self-Driving Car Simulation

![Reinforcement Learning](https://img.shields.io/badge/Reinforcement_Learning-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Self Driving Car](https://img.shields.io/badge/Self_Driving_Car-00B4DB?style=for-the-badge&logo=tesla&logoColor=white)
![DQN](https://img.shields.io/badge/DQN-FF0000?style=for-the-badge&logo=python&logoColor=white)
![Kivy](https://img.shields.io/badge/Kivy-3776AB?style=for-the-badge&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

## Overview
 This project uses Deep Q-Learning (DQN) to train a self-driving car to navigate only on roads while avoiding off-road areas. The reinforcement learning (RL) algorithm helps the car learn from past experiences and improve its decision-making over time.
 The project is built using **Kivy** for GUI rendering and **NumPy** for numerical computations.


## Dependencies
Ensure you have the following dependencies installed before running the project:
```bash
pip install numpy matplotlib kivy pillow
```

## Project Structure
- `map.py`  - Main simulation code that initializes the environment and controls the car's behavior.
- `ai.py`   - Implementation of the Deep Q-Network (DQN) for reinforcement learning.
- `car.kv`  - Defines the UI and graphical elements of the car and its environment.


## Features:
### car.kv
    Car Representation:

        - The car is visually represented using an image (fire_engine.png).
        - It has a size of (22, 12) pixels and rotates based on its angle.

    Sensors for Road Detection:

        - Middle Sensor (Ball1): Green, detects the path ahead.
        - Left Sensor (Ball3) and Right Sensor (Ball2): Red, detect road edges and obstacles.

    Game Environment:
        - Background (my_citymap.png) represents the driving area.
        - The car and sensors are placed at the center initially.

### ai.py

- Neural Network (Network Class) : A three-layer feedforward network with ReLU activation that predicts Q-values for possible actions (left, straight, right).

- Experience Replay (ReplayMemory Class) : Stores past experiences to improve training stability by learning from older transitions.

- Deep Q-Network (Dqn Class) : Uses softmax exploration, updates Q-values via the Bellman equation, and optimizes with Adam (LR = 0.001). Supports model saving/loading (last_brain.pth).

### map.py
Main script for running the self-driving car simulation.
Uses reinforcement learning with a DQN-based AI agent (ai.py).
Defines:

    - Car class: Handles movement, sensors, and collision detection.

    - Game class: Updates game state, AI actions, and reward computation.

    - MyPaintWidget class: Enables user to draw obstacles.

    - CarApp class: Initializes the application and provides UI buttons (clear, save, load).




## How It Works
1. **Initialize the Simulation** : The simulation initializes a 2D environment where a car navigates toward goals while avoiding obstacles.
2. **Sensors & Movement** : The car has three sensors that detect obstacles (sand) and influence movement decisions.
3. **Deep Q-Learning** : The AI is trained using reinforcement learning to optimize navigation strategies.
4. **User Interaction** :
   - Users can draw obstacles (sand) using the drawing tool.
   - Buttons allow clearing, saving, and loading the environment state.
5. **Training & Inference** :
   - The AI learns based on the reward mechanism.
   - The trained model can be saved and reloaded for further improvements.

## Running the Simulation
```bash
python map.py
```

## Controls

- `clear` Button: Reset the environment
- `save` Button: Save the current AI state
- `load` Button: Load the previously saved AI state

## Next Steps
Next, we aim to extend the RL environment to 3D using frameworks like Gym environments. By transitioning to 3D, the model will be able to learn more complex navigation strategies and interact with a more realistic environment.








