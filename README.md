# Self-Driving Car Simulation Using NEAT Algorithm

## Overview

This project implements a self-driving car simulation using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. The simulation uses the Pygame library for graphical rendering and simulates cars navigating a track with the help of evolved neural networks. The neural networks control the car's steering and speed based on sensor data.

## Features

- **NeuroEvolution with NEAT**: Utilizes the NEAT algorithm to evolve neural networks that control the cars.
- **Real-Time Simulation**: The simulation runs in real-time, displaying the cars navigating the track.
- **Sensor Integration**: Cars use simulated radar sensors to detect distances to track boundaries.
- **Fitness Evaluation**: Cars are evaluated based on the distance they travel without crashing.
- **Configurable Environment**: The simulation parameters and NEAT configurations are customizable.

## Requirements

- Python 3.x
- Pygame
- NEAT-Python library

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/self-driving-neat.git
    cd self-driving-neat
    ```

2. **Install the required libraries**:
    ```bash
    pip install pygame neat-python
    ```

3. **Place the required assets**:
    - `car.png`: The sprite image for the car.
    - `map.png`: The image of the track map.
    - `config.txt`: The NEAT configuration file.

## Usage

Run the simulation by executing the main script:

```bash
python main.py
```

## Code Structure

- **main.py**: The main script that sets up and runs the NEAT algorithm and the Pygame simulation.
- **Car Class**: Represents the car with methods for updating position, checking collisions, and drawing.
  - `__init__()`: Initializes the car's attributes.
  - `draw(screen)`: Draws the car on the given screen.
  - `draw_radar(screen)`: Optionally draws the car's radar sensors.
  - `check_collision(game_map)`: Checks for collisions with the track boundaries.
  - `check_radar(degree, game_map)`: Updates the radar sensor readings.
  - `update(game_map)`: Updates the car's position and checks for collisions.
  - `get_data()`: Retrieves the sensor data for the neural network.
  - `is_alive()`: Returns whether the car is still alive (not crashed).
  - `get_reward()`: Calculates the car's fitness reward.
  - `rotate_center(image, angle)`: Rotates the car sprite around its center.

- **run_simulation(genomes, config)**: The main simulation loop where the neural networks control the cars.

## Configuration

The NEAT configuration is stored in `config.txt`. Modify this file to adjust the parameters for the NEAT algorithm, such as population size, mutation rates, and fitness thresholds.

## How It Works

1. **Initialization**: The simulation initializes Pygame, loads the track map, and creates a population of neural networks.
2. **Simulation Loop**: Each generation, the neural networks control the cars based on sensor inputs. The cars navigate the track, and their performance is evaluated.
3. **NeuroEvolution**: The NEAT algorithm evolves the neural networks over generations, selecting for networks that control the cars more effectively.
4. **Rendering**: The simulation visually renders the cars on the track in real-time, displaying information such as the current generation and the number of cars still alive.

## Customization

- **Track and Car Assets**: Replace `map.png` and `car.png` with your custom track and car images.
- **NEAT Parameters**: Adjust the parameters in `config.txt` to fine-tune the evolution process.
- **Sensor and Control Logic**: Modify the `Car` class to change how sensors work or to implement different control strategies.

## Future Improvements

- **Enhanced Collision Detection**: Improve the precision of collision detection for more complex track shapes.
- **Dynamic Difficulty**: Adjust the track difficulty dynamically based on the performance of the neural networks.
- **Multi-Agent Simulation**: Simulate multiple cars interacting with each other to evolve more robust driving behaviors.

## Acknowledgements

- The NEAT-Python library for providing the NEAT implementation.
- The Pygame community for the game development framework.

Feel free to contribute to this project by opening issues or submitting pull requests on GitHub. Happy coding!
