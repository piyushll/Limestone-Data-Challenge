# Tower Research Limestones 2nd Data Challenge: Game of Trust

## Project Overview

This project was undertaken as part of Tower Research Limestones' 2nd Data Challenge. The primary objective is to analyze and reverse-engineer the set of strategies used by players in a simulated game environment. The goal is to determine which strategy is optimal by designing a Monte Carlo simulation where each strategy plays against every other strategy. The reward matrix for the game is provided, and the strategies are ranked based on their performance.

## Data Preparation

The first step involves loading the dataset and encoding the actions using `LabelEncoder`. This helps in converting categorical action labels into numerical values which can be processed by machine learning algorithms.

## Feature Creation

Features are created for all previous actions of both players. This involves generating lag features that capture the history of actions up to the current move. This step is crucial for training models that can predict future actions based on past behaviors.

## Clustering

KMeans clustering is performed on the aggregated strategy features to assign each player to a cluster. This helps in identifying groups of players with similar strategic behaviors.

## Model Training for Each Cluster

Separate RandomForest models are trained for each cluster using all previous actions as features. This allows for the creation of distinct strategy models that can be used in the simulation.

## Monte Carlo Simulation

A Monte Carlo simulation environment is designed where each strategy plays against every other strategy (including itself) for a fixed number of games and rounds. The reward matrix for each round in the game depends on player actions and is used to calculate scores.

## Strategy Ranking

Strategies are ranked based on their average scores from the Monte Carlo simulation. The ranking helps in identifying the most optimal strategy based on the predefined reward matrix.

## Results

The results of the simulation provide a relative ranking of the strategies, starting from the highest reward accruing to the least. This ranking is critical for understanding the effectiveness of different strategies in the game environment.
