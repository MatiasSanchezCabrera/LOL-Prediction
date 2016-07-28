# Predicting the winner of a League of Legends Match at the 10-minute Mark

This was my capstone project for the Udacity Machine Learning Engineer Nanodegree. This project is aimed to predict the winner of a match with the information available at the 10-minute mark and determine which behavior is the most relevant to kill the enemy nexus.

This problem is going to be solved through supervised learning by collecting match data and modeling it as a classification problem where the label variable is going to be defined as ‘Blue win’ and ‘Red win’. Riot Games has a public API where users can get match data like kills, assists, creep score, towers killed and wards placed, among other, which is going to be used to create the dataset. The scope of the analysis in this project is related entirely in team objectives (like Towers, Dragons, etc.) so no information regarding specific champion picks (early game vs late game, assasins vs control mages) is considered.

This repo includes the code necesary to replicate the results. The report with detailed information and findings can be found here: https://www.dropbox.com/s/hb9t1nfc0uhb9ge/Predicting%20the%20Winner%20of%20a%20League%20of%20Legends%20Match.pdf?dl=0


The scripts are described below:

# Game Fetcher.ipynb

This notebook searches for match data by providing seed players and saving the detailed match information in a json file. For each seed player, the script searches for the recent ranked games and saves the specific match information and all the other players involved in that game. After all matches have beeing fetched for that player, the scripts searches for recent ranked games for the fellow players and continues the loop.

If you wish to test this script you will need to provide you Riot Games API Key. Remember that basic keys allow for one request each 1.2 seconds. You will also need the riotwatcher (https://github.com/pseudonym117/Riot-Watcher) library.

# Read Game Data.ipynb

This notebook reads the json files (in my case, aproximatly 16 GBs worth of json files) and prepares the dataset for Machine Learning saving it into a csv file. All objectives are modelled as differences were positive values imply that Blue side had an advantage and negative values imply that Red side had an advantage.

# Data Visualization.ipynb

This notebook reads the data in the excel files and performs basic visualization in order to understand the most important variables to predict the winner of a match. Histograms and Box Plots are calculted in order to make sense of the data.

# Model Training (Diffs).ipynb

This notebook is the one were the magic happens. Different type of models were trained in order to find the predictive function. Some basic understading of scikit learn library is necessary to follow the code. The data is split into training and test samples, models are trained (using Gridsearch) and results are calculated. At the end of the notebook, feature importances are calculted for the best models in order to assess which were the most objectives.



I will be glad to receive feedback or answer any question at matias.sanchez.c@gmail.com as soon as I have the time.

GL & HF!
