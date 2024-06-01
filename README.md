# Flappy Bird NEAT AI

This project demonstrates a Flappy Bird game controlled by an AI trained using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm.

## Libraries

The project uses the following Python libraries:
- **pygame**: For creating the game and handling multimedia.
- **neat**: To implement the NEAT algorithm for training the neural network.
- **random**: For random number generation (e.g., pipe placement).
- **os**: For interacting with the operating system.
- **time**: For controlling the game loop timing.
- **visualize** (optional): For visualizing NEAT networks.
- **pickle** (optional): For saving the best performing neural network.

## Code Structure

The code is organized into several classes and functions:

### Classes

1. **Bird**: Represents the Flappy Bird.
   - Properties: position, tilt, velocity, animation.
   - Methods: movement, jumping, drawing.

2. **Pipe**: Defines the pipes in the game.
   - Properties: location (top and bottom sections).
   - Methods: movement, collision detection with the bird.

3. **Base**: Represents the moving floor of the game.
   - Manages the scrolling effect of the base image.

### Functions

1. **blitRotateCenter**: Rotates an image surface and blits it onto the game window.

2. **draw_window**: Draws various game elements on the screen, including the bird(s), pipes, base, score, generation number, and the number of alive birds.

3. **eval_genomes**: Core of the NEAT training process. Runs a simulation for each bird in the current population, evaluates their performance, and assigns a fitness score.

4. **run**: Sets up the NEAT configuration and runs the training process for a specified number of generations.

## NEAT Training

### Overview

NEAT is an evolutionary algorithm that trains neural networks. Here's a simplified overview:

1. **Population Initialization**: A population of birds (each with a randomly generated neural network) is created.
2. **Evaluation**: Each bird plays the game, with its neural network determining actions based on inputs (bird's position relative to the pipes). Fitness score is based on the distance traveled.
3. **Selection**: Birds with higher fitness scores are more likely to be selected for reproduction.
4. **Reproduction**: Selected birds undergo crossover to create new offspring with potentially improved networks.
5. **Mutation**: A small chance of mutations in the offspring's networks to maintain diversity.
6. **Repeat**: Steps 2-5 are repeated for a specified number of generations.

Over generations, the NEAT algorithm refines the neural networks, leading to birds that navigate pipes more effectively.

## Running the Script

1. **Save the Code**: Save the code as a Python file (e.g., `flappy_bird_neat.py`).
2. **Install Libraries**: Ensure you have the required libraries installed:
   ```bash
   pip install pygame neat-python
3. **Configuration File**: The script includes a configuration file (`config-feedforward.txt`) that defines the NEAT algorithm parameters. Adjust these parameters (e.g., population size, number of generations) to fine-tune the training process.
4. **Run the Script**: Execute the script from the command line:
   ```bash
   python flappy_bird_neat.py
The script will display the game window and start training the bird using NEAT. You will observe the birds' performance improving over generations, eventually learning to navigate the pipes and achieve higher scores.
