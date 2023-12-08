# NBA Player Efficiency Machine Learning Analysis
## Predicting Player Efficiency Rating (PER)
### Author: Millie Cox
#### Date: 12/07/2023

In the realm of NBA basketball, where only five players grace the court for each team simultaneously, the strategic deployment of top-performing athletes is paramount. The quest to more accurately gauge player performance on this elite stage has proven to be a persistent challenge. A notable advancement in this pursuit is the introduction of Player Efficiency Rating (PER), an advanced metric designed to transcend traditional box score statistics. PER strives to unveil the true elements that contribute to a player's value within a team context. My goal is to develop a predictive model for a player's PER rating based on their season-long statistics. Additionally, I aim to discern the specific statistical factors that wield the most influence in forecasting a player's efficiency on the court.

## Background / Motivation

Evaluating the skill level of a basketball player proves to be a complex task due to the multifaceted nature of the sport. Distinguishing between players becomes challenging as two individuals may possess identical statistics yet exhibit vastly different playing styles. In contrast to sports like football or baseball, where success metrics are more straightforward, quantifying success on the basketball court is a nuanced endeavor. For example, comparing a player scoring 30 points per game on 40% shooting with another scoring 20 points per game on 50% shooting lacks a definitive answer to determine the superior player. This ambiguity is where Player Efficiency Rating (PER) becomes invaluable. Serving as an advanced metric, PER endeavors to gauge a player's efficiency on both offense and defense during their on-court engagements. My objective has been to predict PER by leveraging a player's box score statistics and other pertinent metrics.

## Problem statement 

There is a common debate in the NBA about what makes a player valuable on offense to the team. I aim to use Player Efficiency Rating (PER) to determine how effective a player is during their time in the game. Assuming this is an accurate measure of a player’s contribution to the game, I hope to look beyond the box score and uncover what attributes truly make a player ‘efficient’.

## Data sources

I used NBA player data dating back to 1950 from [Kaggle](https://www.kaggle.com/code/piyush1912/nba-top-players-deep-learning/input?select=Seasons_Stats.csv). This dataset gives in depth statistics about players from any year, which helps in determining the variables that are associated with strong PER. Each row represents a season for a player, and the data has 24,700 rows total. Each column represents a different statistic, with 53 columns total. I will use some years to train the model and some as the test dataset. It's important to note that PER as a metric was not adopted until 1952.

## Stakeholders

If PER is truly a reasonable metric to gauge player performance, I will be able to see which factors of a player’s game are most associated their performance on the court and use these to predict a player’s PER given their in-game statistics. This will be valuable to coaches and scouts who can look for desirable attributes in their players and could help make game time decisions and recruit future prospects. Most importantly, a player looking to improve their game will be able to focus on factors most associated with increased player performance. This will both make them more appealing to coaches who are aware of advanced analytics and help them become more efficient on the court. It is worth noting that PER is purely an individual statistic, so it does not account for interactions with other players and team environments. Therefore, simply amassing a group of players that have the traits of high PER players could have adverse effects on the team as a whole, and I was unable to take this limitation into account due to the scope of this project.

## Conclusions and Recommendations

### Overview of models
<html>
<style>
table, td, th {
  border: 1px solid black;
}

table {
  border-collapse: collapse;
  width: 100%;
}

th {
  text-align: left;
}
    

</style>
<body>


<table style="width:100%">
     <colgroup>
       <col span="1" style="width: 15%;">
       <col span="1" style="width: 20%;">
       <col span="1" style="width: 25%;">
       <col span="1" style="width: 40%;">
    </colgroup>
  <tr>
    <th>Ranking</th>
    <th>Model Type</th>
    <th>Test MAE</th>    
    <th>Most Important Features</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Stacking ensemble w/ MARS metamodel</td>
    <td>0.3496</td>    
    <td>OBPM, WS/48, BPM, USG%, WS</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Stacking ensemble w/ XGBoost metamodel</td>
    <td>0.3736</td>    
    <td>Did not calculate</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Stacking ensemble w/ bagged tree metamodel</td>
    <td>0.3804</td>    
    <td>Did not calculate</td>
  </tr>
  <tr>
    <td>4</td>
    <td>XGBoost</td>
    <td>0.4065</td>    
    <td>OBPM, WS/48, BPM, USG%, WS</td> 
  </tr>
  <tr>
    <td>5</td>
    <td>MARS</td>
    <td>0.4209</td>    
    <td>BPM, USG%, WS/48, DBPM, BLK%</td> 
  </tr>
  <tr>
    <td>6</td>
    <td>Voting ensemble</td>
    <td>0.5821</td>    
    <td>Did not calculate</td> 
  </tr>
  <tr>
    <td>7</td>
    <td>Bagged trees</td>
    <td>0.6934</td>    
    <td>OBPM, WS/48, USG%, BPM, OWS</td> 
  </tr>
  <tr>
    <td>8</td>
    <td>Random forest</td>
    <td>0.7263</td>    
    <td>WS/48, OBPM, USG%, OWS, BPM</td> 
  </tr>
  <tr>
    <td>9</td>
    <td>Decision tree</td>
    <td>1.1376</td>    
    <td>OBPM, WS/48, USG%, 3PAr, TS%</td> 
  </tr>
</table>

### Conclusions

- The best model, with a test Mean Absolute Error (MAE) of 0.3496, demonstrates robust predictive capability for Player Efficiency Rating (PER) given the specified predictors, with an error approximately 1/15 of a standard deviation.
- Offensive Box Plus/Minus, Win Shares Per 48 Minutes, Box Plus/Minus, Usage Percentage, and Win Shares emerged as the most critical predictors for PER, with Offensive Box Plus/Minus holding the highest significance.
- Offensive Box Plus/Minus reflects a player's impact on the team's score during their on-court presence. This underscores the notion that offensive performance significantly outweighs defensive contributions in overall player efficiency.
  - In the contemporary league landscape dominated by offensive prowess, players who excel at scoring are highly valued. The emphasis on diverse skillsets for scoring is evident across players of varying profiles.
- The importance of Usage Percentage as a predictor suggests that players who can sustain longer playing times are likely to be more valuable to their teams, contributing to their overall efficiency.

### Recommendations to Stakeholders

- Players are encouraged to enhance their overall shooting proficiency across various facets.
- Coaches and scouts should prioritize recruiting well-rounded shooters over specialists to optimize offensive efficiency.
- The emphasis should be placed on selecting players who exhibit excellent conditioning, allowing them to maximize their on-court involvement.
- Players are advised to prioritize maintaining high-level performance for extended durations, emphasizing the importance of endurance and sustained effectiveness.

### Shortcomings of the Model

- Stakeholders should acknowledge that the model lacks the capability to measure intangibles, recognizing that athlete analysis involves elements beyond the quantifiable variables considered.
- Furthermore, the individual nature of Player Efficiency Rating (PER) means the model cannot capture player-to-player interactions. Exploring the development of a model predicting team efficiency based on individual player statistics could be an intriguing avenue for future research, albeit beyond the current project's scope.