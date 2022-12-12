#NCAA Football Prediction App

This is a series of notebooks created in Google Colab, using the College Football Data (CFBD) Python API (https://pypi.org/project/cfbd/), to predict the margin and score of FBS games. 

##team_game_stats:
This notebook accesses the CFBD Games API to retrieve the stats for each game in a specified year and saves that data to a CSV files.

team_adv_stats:
This notebook accesses the CFBD Stats API to get all FBS teams advanced stats for a specified season. A data frame is created using the data from the API with each row is an individual team and each column is a stat. The data frame is then saved as a CSV file. 

data_cleaning
This notebook outputs a CSV files of all games of FBS vs FBS teams where each line is a game that contains specified advanced offense and defensive stats for the home and away teams. This is achieved by going through each team in the advanced stats data frames, located that teams home games game stats data frame, and using Pandas concatenation function to combine the chosen the stats with the game information. The same is done with the away team data and the final ‘full_stats’ output CSV is created. 

margin_prediciton_model
The ‘full_stats’ CSV data for 11 years of games is read in to this notebook and combined in to one full_data_set and games not marked as completed in the data set is dropped, as well as columns of data points not needed to train the model. The data is then used to train a fast.ai neural network to predict the final score margin for individual games. The model is then saved.  

score_prediciton_model
This notebook works the same as the margin_prediction_model expect the model is trained the find the final point’s total of the home team.

ncaa_prediction_app
In this notebook, the margin and score models are inputted and specified data is first input into the margin model. The data with the predicted margins is then inputted in to the score model. The final information to predict the score of a game contains the predicted home score, the predicted margin, and then the away team score is the difference between the predicted home score and predicted margin. 
