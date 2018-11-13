# NHL-Stats

# Objective
Through data analysis and predictive modelling I attempt to predict NHL regular season game outcomes by utilizing opposing teams prior performance. Through the analysis I will investigate established key performance indicators and their use as predictors of team success?

# Data
NHL data is available via REST API from https://statsapi.web.nhl.com a gitlab repository of all available endpoints and variables contained therein is available here: https://gitlab.com/dword4/nhlapi

All available regular season game data points from the beginning of the 2010 season up to the early 2018 season were retrieved via the API.

I utilized pythons pandas, json and requests libraries to extract and transform game data from the NHL API for analysis and modelling

A variety of NHL data is available covering individual player and team stats, league standings, game outcomes and live feed information highlighting key events during the progression of individual games. For simplicities sake in this project I restricted the scope of analysis to focus solely on team performance per game, variables include:
•	Goals
•	PIM (Penalty minutes) 
•	Shots
•	Power Play % (Goals scored per Power Play Opportunity)
•	Power Play Goals
•	Power Play Opportunities 
•	Face Off Win Percentage   
•	Blocked (Shots from the opposing team blocked by a player reaching the goalie)
•	Takeaways (Intended turnover of possession from the opposing team)
•	Giveaways (Unintended turnover of possession to the opposing team)
•	Hits (Physical contact between opposing players resulting in the loss of possession by the opposite team member)

# Exploratory Data Analysis
I undertook descriptive analysis of game features to better understand the data and to identify any trends which would be indicative of a teams success within a single game or over a period of successive games.
Seasons

<iframe src="https://ciarancarroll.clicdata.com/v/71rHcTZr8rTZ" width="600" height="400" align="middle"></iframe>

During the loading process of game data from the API a number of 404 errors were encountered indicating the specified game data was not available. This was especially prevalent for games in the 2012-13 season.
The 2018-19 season at the time of analysis is underway, results are retrieved regularly and appended to the historical game dataset.
 
Wins per season
 
Excluding current 2018-19 and 2012-13 seasons the distribution of game win percentage centres slightly above 50%. League leaders will rarely hold a game wining average of above 64% and lower end teams can generally be expected to win two out of five games (40%) averaged over a season.
 
Home Team Advantage?
Is there a significant difference for teams playing at their home arena compared to playing away?
 
There appears to be a very slight disadvantage to home teams, a home team in general would be expected to 51% of their away games and conversely 49% of their home games
Certain teams will perform better at home than others

How did you model the data?
Why you chose to model it that way?
What code did you write / use?
How did you fit the model?
How did you validated the model?
How you know the results make sense?
How did you visualized the results?
How you would communicate the results to others?
What did you learn?
What you would do differently if you did this project again?
If you were going to continue this work, what next steps you would take with this project?
How you would explain what you did to a data scientist?
How you would explain what you did to a non-data scientist



NHL API info available here: https://gitlab.com/dword4/nhlapi
