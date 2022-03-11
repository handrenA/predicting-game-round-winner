# Predicting if CT or T wins a round in Counter-Strike Global Offensive

## Background 
Counter-Strike Global Offensive is a multiplayer first person shooter game. The game is divided into two different teams, CounterTerrorist (CT) and Terrorist (T).
The sides consists of 5 player. In order to win rounds T's must either plant the bomb or eliminate all of the CT's. You can choose to play on different maps, and 
each map has it own pros and cons in defending or attacking. 
CT's win the rounds by either defusing the bomb, eliminating all of the T's or letting the time run out. 


## EDA 
In this dataset we can clearly see that the win distrubtions in the different teams are quite similiar. CT's stands for 49% and T's for 51% of the winning rounds.
However, majority of the rounds are not won by planting or winning the rounds. It's actually won by the teams eliminating each other. Finally, there's some advantages of being CT or T on some maps. For instance, there's a higher chance of winning a round as T on de_dust2 & de_inferno, but as a CT maps like 
de_nuke & de_train gives you a higher win rate.

## Feature Engineering 
Since we're dealing with alot of columns in this dataset (i.e 97!), we need to know which feature should be included in this model. By using Gini Importance (MDI)
we can easily plot what feature has the highest mean decrease in impurity. In this feature selection model i proceeded with 15 features, 13 being numerical ones
and 2 being objects. 

## Algorithm selection 
4 Different classifications (with ROC-AUC score) algorithms where tested in this project,
- Random Forest Classifier
- Logistic Regression
- Stochastic Gradient Descent 
- C-Support Vector Classification

Where Random Forest Classifier ended up with the highest score.

## Parameter tuning with Cross Validation Score 
Parameter tuning using both Grid Search and Randomzied Search ended up with a slightly difference in score, where Grid Searchended up with the highest
score 0.9367 vs Randomized 0.9366.

## Model deployment
In real life data was manually collected to try the model if it's accurate enough to predict correct wins. 7 rounds from 5 top teams and 
2 NOT top teams were gathered and tested. The result was following,

ACTUAL winner 
#1.  CT
#2.  CT 
#3.  T
#4.  T
#5.  CT, (Not top team)
#6.  CT, (Not top team)
#7.  T 

PREDICTED winner 
#1.  CT
#2.  CT 
#3.  T
#4.  T
#5.  T, (Not top team)
#6.  T, (Not top team)
#7.  T 




