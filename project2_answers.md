# MATH 475 - Project 2

## By: Brayan Mauricio-Gonzalez & Graham Swain

This markdown file contains our answers for parts 1, 2, and 4 of this assignment.

# Acknowledgements

We did not communicate with anyone besides ourselves about this project.

# Data Set

We chose an NFL data set which has all of the stats of every player from 1970-2021, and if they were on an AP 1st team.
We got this dataset from [https://www.pro-football-reference.com/](https://www.pro-football-reference.com/).

# Features

**year** Year the season took place.

**player** Name of the player.

**tm** Team player was on.

**age** Age of player.

**pos** Position of player (will only be QB in this dataset.)

**g** Games played that season.

**gs** Games started that season.

**wins** Amount of wins player had.

**loses** Amount of loses player had.

**ties** Amount of ties player had.

**pass_rk** Pass Rank, based off of yards. (1 would mean the player had the most passing yards in that season.)

**cmp** Pass completions.

**pass_att** Pass attempts.

**cmp%** Completion percentage.

**pass_yds** Passing yards.

**pass_td** Passing touchdowns.

**td%** Percentage of touchdowns thrown when attempted to pass.

**int** Interceptions thrown.

**int%** Percentage of times intercepted when attempted to pass.

**pass_lng** Longest completed pass.

**pass_y/a** Yards gained per attempt.

**ay/a** Adjusted yards gained per attempt. (Passing yards + 20 * Passing TD - 45 * Interceptions) / Passes Attempted

**y/c** Yards gained per completion.

**pass_y/g** Passing yards per game.

**rate** Quarterback rating.

**sk** Sacks taken.

**yards_lost_sack** Yards lost due to sacks.

**sk%** Percentage of times sacked when attempting to pass. (Sacks) / (Passes Attempted + Sacks)

**ny/a** Net yards gained per pass attempt. (pass_yds - yards_lost_sack) / (pass_att + sk)

**any/a** Adjusted net yards per pass attempt. (pass_yds - yards_lost_sack + (20 * pass_td) - (45 * int)) / (pass_att + sk)

**4qc** Fourth quarter comebacks.

**gwd** Game winning drives.

**rush_rk** Rushing rank. (Based off attempts, not yards.)

**rush_att** Rushing attempts.

**rush_yds** Rushing yards.

**rush_td** Rushing touchdowns.

**rush_lng** Longest rush.

**rush_y/a** Rushing yards per attempt.

**rush_y/g** Rushing yards per game.

**fmb** Times fumbled.

**ap_1st** If they made AP 1st team All-Pro.

**ap_2nd** If they made AP 2nd team All-Pro.

# Target

**AP_1st** - Whether a player is an all pro based on their stats.

# Preprocessing \*

In order to obtain a data set that we are willing to work with, we must scrape data from pro-football-reference. Our ideal data set will have...

# Problem Defintion

This is a classification problem. We're trying to predict whether a player was on an All-Pro 1st team or not based on their stats. More specifically, this is a binary classification problem.

# Performance Metric

We will evaluate the performance of our model(s) using F1-score. This is because an F1-score presents a good balance between precision and recall and gives good results on imbalanced classification problems.

# Bayes Optimum Estimate

Our estimate for the _Bayes Optimum_ on this problem is that a player likely doesn't belong to an All-Pro 1st team. Our justification for our estimate is that there are only a small number of players chosen every season. Because of this, we end up with a lot more players that aren't on an All-Pro 1st team.

# Schedule

-   **Collection of Data (1 hour)**
    -   During this time, we'd solely focus on collecting data for our data set since our inital data set did not have a lot of information
    -   We will web scrape various tables from pro-football-reference
    -   We'd also take the time to clean up our data and make sure it's in a form that can be used to build classification models
        -   This means removing any missing values and converting categorical features into numerical ones through one hot encoding
        -   We'd likely remove any columns that just serve as identifiers, such as name and team
-   **Exploratory Data Analysis (3 hours)**
    -   We would likely spend the first hour of this task just trying to find useful features by hand
        -   We could find statistics about our data such as averages, proportions, maximums/minimums
        -   We could perform various groupby's and see if that gives us more insight
    -   We'd then spend the next two hours plotting data, analyzing the plots, and making note of any useful information for when we begin building models
        -   We would probably create a lot of scatter plots that compare different statistics such as: touchdowns vs assists, where we color the points based on if they were on an All-Pro team or not
        -   We would also plot some bar charts for number of touchdowns, assists, etc. for each position
        -   Through this data analysis, we hope to find out which features are the most useful in predicting if a player will be on an All-Pro team, allowing us to remove the least useful features
-   **Model-Building (3 hours)**
    -   The first half of this task would be spent building various classification models
        -   We'd build logistic regression models, decision trees, random forests, and stacking classifiers
        -   We'd do this by using the various techniques we have learned in class, such as hyperparameter search to determine the best set of parameters for a given model
    -   The second half of this task would be spent comparing the models we created
        -   Using the F1-score of each model, we'd determine which models had the best balance between recall and precision
        -   We'd take the best models and attempt to create new models from them, by either combining them or modifying them slightly
        -   Depending on the accuracy of the best models, we'd pick 1-3 models that best predict our target and focus on those specifically
-   **Wrap-Up (1 hour)**
    -   The last hour of our time would be spent wrapping up anything we'd still be working on at this point
    -   We'd take time to make sure our work is well-documented and clear for any outside readers to understand
    -   We'd ensure that we properly referenced any outside sources and that we gave credit where credit was due

# Work

Our recorded work can be found on _project2_web_scraping.ipynb_.

# Reflection

_How accurate was your time assessment? Was there anything that went significantly longer, or significantly shorter, than you expected?_

_If you were forced to leave the project now and give this plan and this notebook to another person on your team, how useful do you think it would be? What information is missing?_

Three things we learned from this assignment:

-   Thing 1

-   Thing 2

-   Thing 3

_Do you think that this project would be useful to include in future Math 475/575 courses? If yes, why? If no, why not? Are there any specific changes that you would make to this project to make it more informative?_
