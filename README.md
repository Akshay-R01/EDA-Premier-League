# English Premier League ![image](https://user-images.githubusercontent.com/72353918/234956440-ea95ce0d-de11-407a-a4e6-5c43d099e15e.png)

It's one of the most prestigious football leagues in the word. The Premier League is the highest level of the English football league system. Contested by 20 clubs, it operates on a system of promotion and relegation with the English Football League.

We're going to explore its 30 years of history using data analysis.

*Note: Only some of the plots are shown here, to view all of them, they are available in the [Plots Folder](/plots)*

## Dataset
The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/irkaal/english-premier-league-results).

## Language & Libraries
* [Python](https://www.python.org)
* [pandas](https://pandas.pydata.org/docs/index.html)
* [seaborn](https://seaborn.pydata.org)
* [matplotlib](https://matplotlib.org)

### Data Cleaning & Preparation
The dataset was relatively clean. Did the standard cleaning procedure. Dropped NULL Values, used `pandas.describe()` and `pandas.info()` to double check the usabilty. The 'DateTime' column was not of use so the data and month were extracted from the column and then dropped.
The number of Goals was also initialised as a column and the dataframe was grouped by Season was ease of use.

### Initial Observations from a quick scan

* The home team takes more shots & scores more goals on average.
* The away team is more foul commiting.
* The away team also gets more Yellow & Red Cards.
* Most goals scored by one team in a match are 9.
* At most 5 goals are scored at half time.

### Goals per Season
![goals_per_season](https://user-images.githubusercontent.com/72353918/234960665-ddefc76f-fd27-40d9-ad6d-7af1fc841ab1.png)


### Let's get the number of goals per match in a month
Plotted a heatmap by using `seaborn` and using a pivoted dataframe
![goals_match_month](https://user-images.githubusercontent.com/72353918/234960687-9ee5c9bd-e882-4fd6-ad3a-1f38a8dedacc.png)



### Comparison of Shots by Home and Away Teams
![hShots_aShots](https://user-images.githubusercontent.com/72353918/234960741-4c7b05d1-07d2-4b8d-8b93-fec4458c2837.png)

* See how no line intersects. Home goals are always more than Away goals in a season.*There's clearly a home advantage*.
* The number of goals are the lowest in the 2021-22 season (closed door games). Fans clearly play a big role in the games.
* Although the lines are pretty flat, there is a significant drop in shots at target from 2012-13 to 2013-14 season.

### Total Number of Goals scored by the Teams in EPL History
![number_of_goals](https://user-images.githubusercontent.com/72353918/234960768-42f5da0f-8d40-4ac5-8a4d-2482bd1946ea.png)


As we can see,

* Manchester United has scored the highest goals in Premier League since 2000–01 season till date. Sir Alex Feguson the GOAT
* The traditional “big-six” teams occupy the top six positions.
* Bradford has scored the least goals in premier league.

#### To follow this up, let's find the shot conversion rate
Basically we're going to find which team has been the most lethal
![shot_conversion](https://user-images.githubusercontent.com/72353918/234960800-44780bf7-490b-44a5-bffc-ff6f9cfcfdea.png)

* Arsenal is more the most lethal of them all, justifies having canons in their logo
* Hudderfield is the most wasteful with its shots
* Brighton is often talked as one of the most offensive teams which don't convert shots into goals, the plot above proves that.


### Let's see if the "Home Ground Advantage" is Real or just a myth
We'll check the percentage of wins of teams on their ground.
![home_ground_percentage](https://user-images.githubusercontent.com/72353918/234960833-8245cf66-3ac2-470f-a4dd-910b32ce079c.png)


Oh yeah, its real alright


## Now , let's get a deeper dive into the data
### Which referee is the most scary ? 
Who gives out the most red cards ? Who is by the textbook the most?

![referees](https://user-images.githubusercontent.com/72353918/234960878-8103ea6e-5ec3-4596-be59-e2e4525fa649.png)


Whew, Mike Dean being the only one with more than 100 red cards !! Man's gotta chill 
* Mike Dean  along with M Atkinson, P Dowd sure do give a lot of red cards, must be hated by the fans if I had to take a guess :P
* UD Rennie, G Poll, Andy Hall are quite forgiving.

## Comeback Season
The number of times when a team makes a comeback in the match.
Let's see the figures per season
![comebacks](https://user-images.githubusercontent.com/72353918/234960916-3abcf6d9-b04a-4b18-bf4a-96e2b01d0d1a.png)




## Finally, let's plot a Points Table of our own..

We’ll first need to find the following stats for home teams.

* Number of home games played.
* Number of home games won.
* Number of home games drawn.
* Number of home games lost.
* Goals scored and goals against.

1. Generated the necessary fields for the Home & Away team seperately and then was merged by left join, using `pandas.merge()`

2. After the merged dataset is obtained, we'll make a points column with the following criteria
    * +3 for a Win
    * +1 for a Draw
    * +0 for a Loss
    
3. Then the teams were ranked by their points.
Voila!
![points_table](https://user-images.githubusercontent.com/72353918/234960945-a0f8d7a6-578b-462c-9f48-c418af3d0e2a.png)



# There we have it, Exploratory Data Analysis on the Premier League Dataset 
We've gotten a few insights from it, and even more reason to explore more ...

Thanks for reading :)


