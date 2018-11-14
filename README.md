# NHL-Stats

## Objective
Through data analysis and predictive modelling I attempt to predict NHL regular season game outcomes by utilizing opposing teams prior performance. Through the analysis I will investigate established key performance indicators and their use as predictors of team success?

## Data
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

## Exploratory Data Analysis
I undertook descriptive analysis of game features to better understand the data and to identify any trends which would be indicative of a teams success within a single game or over a period of successive games.

### Seasons

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/71rHcTZr8rTZ" width="600" height="400" frameBorder="0"></iframe></p>

During the loading process of game data from the API a number of 404 errors were encountered indicating the specified game data was not available. We would expect to retrieve 1,230 games prior to the 2017 season and 1,371 2017 onwards (Las Vegas Golden Knights  entered the league in 2017). The missing games were especially prevalent for games in the 2012-13 season. The 2018-19 season at the time of analysis is underway, results are retrieved regularly and appended to the historical game dataset.
 
### Wins per season

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/KlNzwKdr8QX9" width="600" height="400" frameBorder="0"></iframe></p>

Excluding current 2018-19 and 2012-13 seasons the distribution of game win percentage centres slightly above 50%. League leaders will rarely hold a game wining average of above 64% and lower end teams can generally be expected to win two out of five games (40%) averaged over a season.

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/qt3DbSInCncX" width="400" height="400" frameBorder="0"></iframe></p>
 
### Home Team Advantage?
Is there a significant difference for teams playing at their home arena compared to playing away?

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/cP22UwI6i0QR" width="600" height="400" frameBorder="0"></iframe></p>

There appears to be a very slight disadvantage to home teams, a home team in general would be expected to 51% of their away games and conversely 49% of their home games

Certain teams will perform better at home than others, illustrated below is the variance of home and away Win % from overall performance.

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/hXQWCBEpVPMo" width="600" height="400" frameBorder="0"></iframe></p>

Lets take a look at goals scored for home and away teams

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/L089afYFySCv" width="600" height="400" frameBorder="0"></iframe></p>

It appears that home teams score a higher number of goals per game more frequently than away teams, this would indicate a wider margin for home team wins than losses

By conducting a paired t-test on the distribution of home and away goals, we can establish if there is a statistically significant difference between the two populations

Ttest_relResult(statistic=11.135112011475373, pvalue=1.2859551452133143e-28)

The pvalue of the t-test being less than 0.05 we can reject the null hypothesis that there is no difference home and away teams in respect of goals scored

### Corsi Stats

Lets look at shots (on goal, missed and blocked), a popular metric is the Corsi which compares shots for and against and can be represented as a integer or percentage

For example Team A have 66 shots on goal Team B have 55: Corsi Team A = 66-55 = 11 Corsi Team A% = 66/(66+55) = 55% Corsi Team B = 55-66 = -11 Corsi Team B% = 55/(66+55) = 45%

<p align='center'><iframe src="https://ciarancarroll.clicdata.com/v/r1QzPCFSTvON" width="600" height="400" frameBorder="0"></iframe></p>

If we compare teams Win% and Corsi% we can see a correlating trend between the two, by calculating the correlation coefficient we see a moderate correlation between the two:

from scipy.stats.stats import pearsonr
pearsonr(corsi_grouped['Corsi %'],corsi_grouped['Win %'])

(0.6184222739960428, 0.00020899389348708302)
(Coefficient, P value for testing of non-correlation)

### 

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
