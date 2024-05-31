# Traveling Salesman Problem Solver Using Genetic Algorithm

This project provides a solution to the Traveling Salesman Problem (TSP) using a Genetic Algorithm (GA). The algorithm evolves a population of potential solutions over a series of generations, selecting, crossing, and mutating individuals to find the shortest possible route that visits each city once and returns to the starting point.

## Requirements

This script requires Python 3.x to run.

## Overview

The main components of the implementation are:
1. **Initialization**: Generate an initial population of potential solutions.
2. **Fitness Evaluation**: Calculate the fitness of each individual based on the total distance of the path.
3. **Selection**: Select the fittest individuals to form the basis of the next generation.
4. **Crossover**: Combine pairs of individuals to produce offspring.
5. **Mutation**: Apply random changes to individual solutions to maintain genetic diversity.
6. **Evolution**: Repeat the selection, crossover, and mutation processes over multiple generations to improve solutions.

## Code Structure

### Classes and Functions

- **`chromo`**: A class representing a chromosome with a path and its fitness value.
- **`fitness(chromo)`**: Calculates the fitness (total distance) of a given path.
- **`apartheid(population, number)`**: Selects a subset of the population.
- **`tournament_selection(population, tournament_size)`**: Selects the fittest individuals using tournament selection.
- **`order_crossover(parent1, parent2)`**: Combines two parent paths to produce offspring using order crossover.
- **`mutation(individual)`**: Applies mutation by swapping two cities in the path.
- **`generate_path(genes)`**: Generates a random path starting and ending at the same city.
- **`make_pop(population, genes)`**: Creates the initial population of chromosomes.
- **`pop_score(population)`**: Computes the total fitness score of the population.
- **`create_offspring(fittest)`**: Generates a new generation from the fittest individuals.
- **`main()`**: The main function to run the genetic algorithm.

### Genetic Algorithm Parameters

- `popSize`: The size of the population (default: 100).
- `mutation_rate`: The mutation rate (default: 3).
- `max_gens`: The maximum number of generations (default: 10).
- `threshhold`: The fitness threshold to stop the evolution (default: 600).
- `selection_size`: The number of individuals selected for breeding (default: 5).

### Cities and Distances

The cities and distances between them are represented in a graph:

```python
nodes = 7
pos = {"A":0, "B":1, "C":2, "D":3, "E":4, "F":5, "G":6}
GENES = "ABCDEFG"
graph = [[0, 90, MAX, 300, 140, MAX, 220],
         [100, 0, 80, MAX, MAX, 300, 150],
         [MAX, 340, 0, 40, 250, MAX, MAX],
         [360, MAX, 240, 0, 80, 170, MAX],
         [450, 40, MAX, MAX, 0, MAX, 100],
         [70, MAX, 330, 160, MAX, 0, 110],
         [MAX, 320, 140, 90, 280, 190, 0]]
```

## Running the Code

To run the script, simply execute it in a Python environment:

```bash
python tsp_ga.py
```

The script will print the evolution of the population, showing the fittest individuals and their fitness scores at each generation. The shortest path found will be displayed at the end.

## Example Output

```
Generation No:  1
Score:  15800

Fittest:
Path        Fitness
...
Shortest Distance Found: ABCDEFG 650
```

## Notes

- Ensure that all necessary libraries are installed (e.g., `random`).
- The algorithm parameters (population size, mutation rate, etc.) can be adjusted for different performance characteristics.
- The implementation uses simple data structures and can be extended or optimized for larger datasets or different crossover/mutation strategies.
