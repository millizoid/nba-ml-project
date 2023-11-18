# nba-ml-project

## Background / Motivation

There are numerous intricacies in evaluating a basketball player's skill level due to the multifaceted nature of the sport. Unlike football or baseball, where success is often quantifiable through clear statistics, basketball's subjective nature poses challenges in objectively measuring player success on the court. For example, comparing a player scoring 30 points per game on 40% shooting to another scoring 20 points per game on 50% shooting lacks a definitive answer on who the superior player is. Enter Player Efficiency Rating (PER), an advanced metric designed to gauge a player's efficiency in both offense and defense during their time on the court. My objective is to predict PER based on a player's box score statistics and other pertinent metrics.

## Problem Statement

A prevalent debate in the NBA revolves around what truly makes a player valuable on the offensive end for their team. Leveraging Player Efficiency Rating (PER), I aim to assess a player's effectiveness during their time in the game. Assuming PER is an accurate measure of a player's contribution, my goal is to delve beyond traditional box score metrics and discern the attributes that genuinely define a player as 'efficient.'

## Data Sources

I utilized NBA player data dating back to 1950 from [Kaggle](https://www.kaggle.com/code/piyush1912/nba-top-players-deep-learning/input?select=Seasons_Stats.csv). This comprehensive dataset provides detailed statistics about players from any given year, aiding in the identification of variables associated with a high PER. Each row represents a player's season, resulting in a total of 24,700 rows, and each of the 53 columns represents a different statistic. Some years were used for model training, while others served as the test dataset. Notably, PER as a metric was not adopted until 1952.

### Data Cleaning/Preparation

- Removed meaningless columns (`blanl`, `blank2`, `Unnamed: 0`).
- Excluded irrelevant columns (`Year`, `Player`, `Tm`).
- Converted the remaining categorical variable, `Pos`, into dummy variables.
- Eliminated variables affected by game performance (`G`, `GS`, `MP`).
- Dropped rows with null values for streamlined analysis.
- Split the data into an 80-20 train-test split.

### Distribution of Response

The response variable (PER) exhibits an approximate normal distribution with a mean of 13.2 and a standard deviation of 4.7.

### Correlations

- The correlation matrix indicates a predominantly positive correlation of most variables with PER.
- PER demonstrates the strongest correlation with variables measuring performance, such as `WS/48` (Win Shared / 48 mins) and `BPM` (box plus/minus).
