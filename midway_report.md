# Semester Project - NBA and Machine Learning

## Question Formulation:

- **What is the specific question you're aiming to answer with your data?**

Is PER (Player Efficiency Rating) the most accurate/reflective number for an NBA Player's performance?

- **How did you arrive at this question, and why do you believe it holds significance or interest for a larger audience?**

In the realm of basketball analytics, a pivotal inquiry looms large: Is Player Efficiency Rating (PER) the most accurate gauge of an NBA player's performance? This question holds significant weight, resonating not only within the basketball community but also reaching into the broader landscape of sports evaluation and statistical methodologies. As the basketball world increasingly embraces advanced analytics to dissect player contributions comprehensively, understanding the precision and relevance of a prominent metric like PER becomes paramount. The answer to this question carries implications beyond individual player assessments, influencing team strategies, trade decisions, and shaping the discourse around statistical benchmarks in professional sports. In an era where data-driven insights are integral to decision-making, scrutinizing the role and accuracy of PER stands as a key endeavor that can reshape how enthusiasts, analysts, and team executives perceive and quantify player excellence.

- **What challenges, if any, have you faced in narrowing down or refining your question?**

Some challenges that I have had in narrowing this question down was figuring out what I was actually wanting to answer. I originally had a few different question ideas, all of which I liked. This question was the one that I chose because I was able to get the necessary data to answer it, yet still have flexibility in what I wanted to inlcude.

## Data Aquisition

- **From where have you sourced your dataset?**

I used NBA player data dating back to 1950 from [Kaggle](https://www.kaggle.com/code/piyush1912/nba-top-players-deep-learning/input?select=Seasons_Stats.csv), and this data was scraped from season stats from [Basketball Reference](https://www.basketball-reference.com). This is a very common and reliable source to get data on the NBA, as well as other collegiate and professional leagues. 

- **Briefly describe the dataset in terms of size, features, and nature of the data (numerical, categorical, time-series, etc.).**

This dataset gives in depth statistics about players from any year, which helps in determining the variables that are associated with strong PER. Each row represents a season for a player, and the data has 24,700 rows total. Each column represents a different statistic, with 53 columns total. I will use some years to train the model and some as the test dataset. It's important to note that PER as a metric was not adopted until 1952.

- **Have you ensured the dataset's legality and credited its source appropriately? Provide a brief overview of your verification process.**

Yes. The Kaggle Dataset is connected to another project in which the author states that the data used was legally obtained through manually scraping Basketball Reference, and the data can be used by others. Basketball Reference's policy on using their data is consistent with this as well.

- **Were there any challenges or obstacles in finding the right dataset for your project?**

Yes. 

## Data Analysis and Model Building (Preliminary Stages):

- **What steps of preprocessing have you undertaken so far?**

- Data Cleaning/Preparation
- Removed meaningless columns (blanl, blank2, Unnamed: 0).
- Excluded irrelevant columns (Year, Player, Tm).
- Converted the remaining categorical variable, Pos, into dummy variables.
- Eliminated variables affected by game performance (G, GS, MP).
- Dropped rows with null values for streamlined analysis.
- Split the data into an 80-20 train-test split.

- **What insights or patterns have you observed during your initial data exploration?**

- Correlation matrix shows that most variables positively correlated with PER.
- PER is most correlated with variables similarly measuring performance, such as `WS/48` (Win Shared / 48 mins) and `BPM` (box plus/minus).
- The response variable (PER) is approximately normally distributed with mean 13.2 and standard deviation 4.7.

- **If you've started feature engineering, which features have you created or modified, and why?**

Something that I want to include in this model is the home/away win ratio or percentages. This is something that is not included in the original data, but I could either source from an external source or perform some manipulation. I have not seen a feature like this included in a model

- **Which machine learning models or techniques are you currently considering or have already started implementing?**

Random Forest, Bagged Trees, XGBoost, voting ensembles. Currently, I am exploring how different models are reacting with the data to choose one overall

- **If you've applied any models, what preliminary results or insights have you obtained?**

- Offensive Box Plus/Minus delves into a player's impact on the court, drawing from their box score statistics. For instance, in a game where a team loses by 10 points, if a player registers a plus/minus of +10, it indicates that their team outscored the opponents by 10 points during their time on the court.
- The key insight for players lies in recognizing that offensive performance carries more weight than defense in determining overall player efficiency.
- This perspective aligns with the current landscape of the league, which is increasingly characterized by offensive dominance. In today's basketball climate, players who excel in scoring are often held in higher regard, prompting athletes of diverse profiles to diversify their skill sets and enhance their scoring abilities.

## Deliverables:

- **Share the link to your current GitHub repository.**

https://github.com/millizoid/nba-ml-project.git

- **What sections or contents have you included in your Readme.md file thus far?**

Background, problem statement/question, data sources, EDA findings (I'm still adding the code), data cleaning (NOTE: THIS IS ALL IN `midway-point` branch)

- **Describe the organization and documentation style of your current codebase.**

Right now it is mostly organized in data sourcing, data cleaning, eda, and then building the model. The code has been commented well throughout, and I am currently working on adding more narrative and documentation into markdown to go along with this. My overall goal is to take the narrative and focus more on that and have the code supporting it.

- **Have you started on the feedback and iteration process file? If so, what feedback or iterations have been documented?**

Yes. Probably the biggest thing that I have documented and been working on is deciding what to actually include in the model and how that influences what the results actually mean.

## Challenges and Learnings:

- **What has been the most challenging part of the project so far?**

The most challenging thing for me has been deciding what to include in this model. With my dataset having 54 variables, there are a lot of things that I can consider with player efficiency. For example, a big question that I need to decide on is what my overall decision on team stats will be versus individual and how that plays into if PER is accurate.

- **Have you had to pivot or adjust any aspects of your project based on unforeseen challenges or insights?**

Yes. My original question was more focused on team performance and evaluating that. Individual performance was a big part of team performance evaluation, and I had to pivot from focusing on the team to individual players. One  of the most important reasons that I decided to do this was because it allowed me to more fully understand the variables that I was working with, therefore allowing me to make more educated decisions.

- **What do you believe will be your next steps in the coming weeks?**

Over the next few weeks, the project will embark on a two-fold exploration. First, the focus will be on refining feature engineering to create a more nuanced representation of Player Efficiency Rating (PER). This entails a comprehensive analysis of the dataset, looking beyond conventional metrics to capture the multifaceted nature of player contributions. The goal is to uncover latent patterns and relationships that can significantly enhance the predictive power of the model.

Simultaneously, there will be an in-depth investigation into the selection and optimization of machine learning models. This step involves a meticulous examination of various algorithms to discern the most suitable ones for modeling the intricate dynamics of NBA player performance. The objective is to build a robust model that not only accurately predicts PER but also provides valuable insights into the underlying factors that contribute to a player's efficiency on the basketball court.

The upcoming weeks will thus be dedicated to a data-driven and iterative exploration, aiming to enhance the accuracy and interpretability of the model, ultimately providing a more nuanced understanding of what defines player efficiency in the NBA.

- **Are there any areas where you might need additional resources, guidance, or clarification?**

As I dive into the next phases of the project, I might need some extra help and pointers in a few spots. Exploring fancy new tricks for feature engineering could get a bit tricky, so some guidance from the experts or cool resources could make that smoother. Choosing the best machine learning models might also need a bit of hand-holding, especially with complex ones, to make sure we're on the right track. Basketball stats have their own language sometimes, so some extra insight into the game's analytics or a chat with someone in the field could clear up any confusion.

## Collaboration and Feedback

- **If you've sought feedback from peers, mentors, or others, what feedback have you received, and how have you incorporated it?**

There have been two main pieces of feedback that I have received: 1) try to include feature engineering and 2) stay consistent in deciding what variables to include. I am incorporating this feedback by seeing if there is a way to create a model that stays consistent in what I am trying to meaure through using feature engineering techniques

- **How are you ensuring effective collaboration if the project is being done in a team setting?**

Something that I have found really useful in doing is not only talking about my project (because I know the data that I am using more than others), but seeing how it relates to what others are doing with their projects. Even though I am not working on the same project as others, seeing how they handle data and creatively use it has given me lots of ideas.

## Timeline and Goals

- **Do you believe you're on track to complete the project by the end of the semester? If not, what are the bottlenecks or delays?**

Yes. I currently feel like I am in a very good place. The rest of the semester/this project is going to be focused more on improving the methods I am using for this rather than actually building and interpreting the model.

- **Outline the milestones you aim to achieve in the next few weeks.**

- Investigate more into how I can feature engineer stats such as player home efficiency/player away efficiency
- Write up and put visuals of the EDA, data sourcing, cleaning, and preprocessing that I have done and put into final report
- Choose model to use