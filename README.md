# Recommender-Systems-Competition-Project-2022-2023

## Goal

The application domain is TV shows recommendation. The datasets we provide contains both interactions of users with TV shows, as well as features related to the TV shows. The main goal of the competition is to discover which items (TV shows) a user will interact with.
Each TV show (for instance, "The Big Bang Theory") can be composed by several episodes (for instance, episode 5, season 3) but the data does not contain the specific episode, only the TV show. If a user has seen 5 episodes of a TV show, there will be 5 interactions with that TV show. The goal of the recommender system is not to recommend a specific episode, but to recommend a TV show the user has not yet interacted with in any way.

## Description

The datasets includes around 1.8M interactions, 41k users, 27k items (TV shows) and two features: the TV shows length (number of episodes or movies) and 4 categories. For some user interactions the data also includes the impressions, representing which items were available on the screen when the user clicked on that TV shows.
The training-test split is done via random holdout, 85% training, 15% test.
The goal is to recommend a list of 10 potentially relevant items for each user. MAP@10 is used for evaluation. Any kind of recommender algorithm written in Python can be used.

## Solution

Many different recommendation algorithms were tested, also merging them through different hybrid approaches. The final solution, which has leaded to the best submission score, consists in a hybrid recommender system merging 3 base recommenders (weighting the similarity matrices). The base recommenders are:

* SLIM Elastic-Net
* EASE-R
* RP3Beta

Bayesian search approach has been implemented to find the optimal hyperparameters (single recommenders hyperparameters and similarity matrix weights). Our final solution has achieved these following results:

* Baselines: 5/5 passed
* Public Leaderboard: 27/83 (MAP@10: 0.05949 - highest in the competition: 0.06259)
* Private Leaderboard: 25/83 (MAP@10: 0.05889 - highest in the competition: 0.06213)

## Additional information

* The project has been developed in a team of two, composed by me and [@shalbyhazem99](https://github.com/shalbyhazem99).


* The proposed solution has been implemented using and adapting algorithms from the official Recommender Systems [course repository](https://github.com/MaurizioFD/RecSys_Course_AT_PoliMi).
