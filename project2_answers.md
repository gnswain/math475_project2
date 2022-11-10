# MATH 475 - Project 2

## By: Brayan Mauricio-Gonzalez & Graham Swain

This markdown file contains our answers for parts 1, 2, and 4 of this assignment.

# Acknowledgements

We did not communicate with anyone besides ourselves about this project.

# Data Set

We chose an NFL data set which has all of the stats of every player from 1970-2021, and if they were on an AP 1st team.
We got this dataset from [https://www.pro-football-reference.com/](https://www.pro-football-reference.com/).

# Features

**1st team all-pro** - On the player and team pages, the words "all-pro" now mean first-team all-pro, according to the Associated Press all-pro team from 1940--present or the UPI team from 1931--1939.

**2PM** - two-point conversions made.

**A/G** - attempts (either passing or rushing) per game.

**ANY/A** - adjusted net yards per passing attempt: (pass yards + 20*(pass TD) - 45*(interceptions thrown) - sack yards)/(passing attempts + sacks). See AY/A.

**AP1** - the number of times the player was named first team all-pro.

**Ast** - assists on tackles. See tackles. Pre-1994, assists are grouped with tackles. From 1994 to the present, they remain an unofficial stat, but are recorded consistently and should be complete in our database.

**Att** - attempts. If in a rushing table, this is rushing attempts. If in a passing table, it means passing attempts.

**AV** - approximate value. This is our attempt to put a single number on each player-season since 1960 so that we can (very approximately) compare across years and across positions. See this About page for all the details.

**AvRk** - on coach's pages, this number is the average finish, within the division, of that coach's teams.

**AY/A** - adjusted yards per passing attempt: (pass yards + 20*(pass TD) - 45*(interceptions thrown))/(passing attempts). This stat was introduced, and the reasoning behind it thoroughly explained in a book called The Hidden Game of Football, by Bob Carroll, Pete Palmer, and John Thorn. Note that we are now using 20 yards per TD instead of 10.

**BB (position)** - blocking back (in the single wing).

**Blck** - punts had blocked.

**Cmp%** - completion percentage: completions/(passing attempts).

**Expected W-L** - this is an estimate of what the team's record "should have been," given the team's points scored and allowed. The concept goes back to baseball analyst Bill James' Pythagorean formula.

**Expected Points** - expected points represent the estimated point value at the start of a given play, based on down, distance, and field position. Further explanation of the formula is on our blog.

**FantPos** - fantasy position. This is (for now) always either QB, RB, WR, or TE. The reason we need this column is that, to compute VBD, every player needs to be classified as one and only position. It gets a bit problematic for players like Eric Metcalf who played different positions at different points in their career. If you see a player-season that is misclassified, please let us know.

**FantPt** - fantasy points:

-   Passing Yards: 1 point per 25 yards passing
-   Passing Touchdowns: 4 points
-   Interceptions: -2 points
-   Rushing Yards: 1 point per 10 yards
-   Rushing Touchdowns: 6 points
-   Receiving Yards: 1 point per 10 yards
-   Receiving Touchdowns: 6 points
-   Return Touchdowns: 6 points
-   Fumble Recovered for a Touchdown: 6 points
-   2-Point Conversions: 2 points
-   Fumbles Lost: -2 points

**FF** - forced fumbles. We are still working on integrating this into our data set.

**FGA** - field goals attempted.

**FGM** - field goals made.

**FL (position)** - flanker.

**Fmb** - fumbles. This includes all fumbles, including those that were recovered by the fumbler's team.

**FR** - fumble recoveries.

**G** - games played.

**GS** - games started. This is complete from 1980 forward, and partially complete before that.

**Int** - in a passing table, this means interceptions thrown. In a defensive table, it means interceptions caught.

**LH (position)** - left halfback.

**Lng** - long gain. This was the player's (or team's) longest gain of the season in that particular category.

**LS (position)** - left safety.

**MG (position)** - middle guard (in a 5-2 defense).

**NY/A** - net yards per passing attempt: (pass yards - sack yards)/(passing attempts + sacks).

**OthTD** - other TDs: all touchdowns that were not rushing, receiving, kickoff return, punt return, interception return, or fumble return touchdowns.

**OvRank** - overall rank (for fantasy football). This denotes the player's overall rank (among all players, not just those at his position) for that season. See also VBD and fantasy points.

**PB** - the number of times the player was a pro bowler.

**PD** - passes defensed. A relatively new stat. We are still working on integrating it into our data set.

**Pnt** - punts.

**Pos** - position. Note that this is upper-case if the player was his team's primary starter at the given position, it is lower-case if the player started some games but was not his team's primary starter. It is blank if the player did not start very many games (or none at all). There are no hard-and-fast rules for exactly who gets classified as a primary starter, a part-time starter, or a non-starter, but the information has been provided to us by the editors of the ESPN Pro Football Encyclopedia, who have made these designations after much research.

**PosRank** - position rank (for fantasy football). This denotes the player's rank within his position for that season. See also VBD, fantasy points, and OvRank.

**Pro Bowler** - A player is considered a pro bowler if he was named to the pro bowl as a starter, a reserve, or an injury replacement. If named to the team, a player is considered a pro bowler even if he does not attend the pro bowl due to injury.

**R/G** - receptions per game.

**Rate** - passer rating. Note that pro and college football use different formulas. Some details can be found here and you can calculate a passer rating using our NFL Passer Rating Calculator Tool.

**Rec** - receptions.

**RH (position)** - right halfback.

**RRTD** - rushing TDs plus receiving TDs.

**RS (position)** - right safety.

**SE (position)** - split end.

**Sk** - in a passing table (1969--present), this refers to times sacked. In a defensive table, it refers to the number of sacks a player or team made. For individuals, sacks have only been an official stat since 1982.

**Sk%** - sack percentage: (times sacked)/(passing attempts + times sacked).

**SoS** - Strength of Schedule indicates the combined winning percentages of the opponents this team played in a given year. Higher SoS indicates a tougher schedule, lower indicates easier.

**SRS** - Simple Rating System, explained in this blog post, uses a team's point differential and strength of schedule to assign a rating to each team, with 0.0 considered average. The difference in two teams' SRS ratings can be considered to be a point spread should they play each other, disregarding home field advantage.
St - the number of seasons in which the player was his team's primary starter at his position.
Targets - pass targets, as given in the play-by-play account of the game. Note that pass locations are defined as long (15 or more yards) or short (less than 15 yards).

**T/G** - in the team stats section of a coach's page, this denotes the team's takeaway/giveaway rank.

**TB (position)** - tailback (in the single wing).

**TD** - touchdowns.

**TD%** - passing TD percentage: (passing TD)/(passing attempts).

**Tkl** - tackles. We have tackle data for all players who were active in 1994 or later. Prior to 1994, the tackle data is unofficial, inconsistently recorded from team to team, and incomplete in our database. Also, before 1994, some teams recorded assists while others didn't, so we have lumped tackles plus assists together in the tackles column for those years. From 1994 to present, tackles remain an unofficial stat, but are recorded consistently and should be complete in our database.

**VBD** - the player's fantasy value for the season. VBD stands for Value-Based Drafting, but the initials have come to stand for the result of the method (i.e. the value of the player) in addition to the method itself. The method was popularized by Joe Bryant of footballguys.com in the early 90s.

Essentially, the idea is this: the value of a player is the difference between his fantasy points and a baseline, with the baseline being defined as the number of fantasy points that a relatively cheap replacement would get. I've defined the baselines as the fantasy point totals of the #12 QB, the #24 RB, the #30 WR, and the #12 TE for each season. I won't go into detail on why I chose these numbers, but if you are a fantasy footballer, you probably have some idea.

Anyway, here's an example. In 1975, O.J. Simpson had 362 fantasy points. The #24 ranked running back that year was John Brockington who had 116 fantasy points. Thus, O.J.'s value for 1975 is defined to be 362 - 116, which is 246. But wait, there's just one more thing. Since the NFL schedule was only 14 games long back in those days, I'll multiply that 246 by 16/14 to get 281 (I've also adjusted the values for the strike-shortened seasons of 1982 and 1987 in this way).

NOTE: any player who is below the baseline will be counted as having zero value.

**wAV** - weighted career approximate value. See the entry on AV. The weighted career AV is computed by summing 100% of the player's best-season AV, 95% of his second-best-season AV, 90% of his third best, and so on. The idea is that the weighted career AV rating should weight peak seasons slightly more than "compiler"-type seasons.

**WB (position)** - wingback (in the single wing).

**XPA** - extra points attempted.

**XPM** - extra points made.

**Y/A** - yards per attempt.

**Y/C** - yards per completion.

**Y/G** - yards per game.

**Y/R** - yards per reception.

**Yds** - yards.

**YScm** - yards from scrimmage. That is, rushing yards plus receiving yards.

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
