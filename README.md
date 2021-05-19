# 2021_NBAplayers_Clustering-Regression-_Project

  *As a huge sports and basketball fan, I wanted to work on a project the involed basketball players and statistics. My goal for this project was to really dive into what seperates ever player interms or play style. This was a challenging iterative tio understand what variable I wanted to use to get the best results for each case. By delving deep into the statistics of the players I was able appriate all my favorite players even more by understaing the crux of there playStyles.*
# NBA players Clustering/Regression Project(Based on 2020/2021 season): Overview
- Used KMeans from sklearn to cluster players to analyse similar play styles, see how good a player is, and determine if the traditional PPG, AST and RPG are good ways to jusge a player.
- Cleaned and organized data in Pandas to create the best possible Data Frame to use for exploratory data analysis and model building.
- Used Seaborn and Matplotib to determine which stats were best fit to use in our clusters and our regrassion models. 
- Created models: Multiple Linear Regression with test and train cases and determined best Height and Weight for Offensive Rebounts and Defencive rebounds in the NBA. 
- Created model the Predicts Points per game but looking at other game and pysical statistics.




## Code
**Python**: Version 3.7.6    
**Packages**: Numpy, Pandas, Kmeans, Sklearn, matplotib, selinium, seaborn   
**Tableau**: https://public.tableau.com/profile/samruth.vennapusala#!/


## Resources
**Data Acquisitions Websites:**  
https://www.basketball-reference.com/leagues/NBA_2020_totals.html  
https://www.nba.com/stats/teams/traditional/?sort=W_PCT&dir=-1  
https://www.nbastuffer.com/2020-2021-nba-player-stats/   

## Data Cleaning
We took 3 different data sets from different sources and cominded them under one dataframe With Pandas. There was a lost of cleaning to with this data set before we could proceed to the Explorotory Data Analysis, Data Clustering and our Models. We had to make sure that the Heights and weights were in the correct readable formats and got rid of all the excessive verbage. We made sure that all the numerical data was in the right forms witht he correct units. We also had to make sure the worded data was also all in the same format. There were also issues with players shoing up multiple times because they got traded half way through the season to another team. We made sure to combine the data to best represent the player. Here is the final data set the we used for the rest of our project.

https://github.com/samruthv/2021_NBAplayers_Clustering-Regression-_Project/blob/main/Data%20Cleaning/total_Stats.csv

**The Data Sets:**
[#,	Player,	Team,	GP,_x	MPG,	FGM, FGA,	FG%,	3PM,	3PA,	3P%,	FTM,	FTA,	FT%,	TOV,	PF,	ORB,	DRB,	RPG,	APG,	SPG,	BPG,	PPG,	TEAM,	AGE,	WEIGHT,	COLLEGE,	COUNTRY,	DRAFT YEAR,	DRAFT ROUND,	DRAFT NUMBER,	GP_y,	PTS,	REB,	AST,	NETRTG,	OREB%,	DREB%,	USG%,	TS%,	AST%,	HEIGHT,	Position,	SALARY]

*The '#' represents the rank of the player on their given team. This is an opinionated rank given by one of the website. The rest of the data are factual data from officaal sorces.*   


## Exploritory Data Analysis

Between all the columns of data the we aquired, we wanted to see what the relationship between all the vectors were before we got to the clustering and the modeling aspect of the project.

Firstly here are pairplots and heatplots of the different columns of data.

<p align="center">
  Heatmaps
</p>
<p align="center">
   <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/Dataset1_heatmap.png" width="400" > <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/Dataset2_heatmap.png" width="387"  >
</p>
<p align="center">
  Pairmaps
</p>
<p align="center">
   <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/Stats_Correlation_pairplot.png" width="400" > <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/DATA2_pairplots.png" width="401"  >
</p>


*Double click the maps to open the picture in a new tab to get a clearer picture*    

There is a lot to break down with these tables. There are a lot of statistics with stong positive coorilation, some with negative coorilation and some that are not coorilated at all. for example:

<p align="center">
  TOV vs APG    |     FT% vs BPG    |     3P% vs ORB
</p>
<p align="center">
  Strong Positive coorilation    |     No Coorilation    |     Slight Negative Coorilation
</p>

 

<p align="center">
   <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/TOV_vs_APG.png" width="250" > <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/FT%25_vs_BPG.png" width="250" > <img src="Exploratory%20Data%20Analysis/EDA_IMAGES/3P%25_VS_ORB.png" width="250" > 
</p>
 
We also looked at the physique of the players   
Height VS Weight     

<img src="Exploratory%20Data%20Analysis/EDA_IMAGES/Weight_VS_Height.png" width="250" >

## Clustering

Our nexzt step we performed 2 demintional and multidementional clustering with K-means to see how well we can predict the orginal data with our model.

The first situation the we were able to cluster and evaluate in tablue was our Height vs. Weight. In this model we were able to predict the position that a player played with 73.2% accuracy.



We then move onto more complex clustering models in python. One of the situations we were trying to cluster were the type of players. This was a difficult task becuase we did not want k-means to cluster the players who get more playing time to less playing. If we used all the variables our medel just seperated the players by who put up more higher stats vs lower states. We did not want this. What we want was to cluser by play style. So the 'catch and shoot player', 'big man', 'facilitators', 'all rounded'and ect get paired together. For us to get this result, we could not include any variables that were coorealted to playing time. So for example instead of using 3 points made, we would use 3 point percentage. This was a very itterative process and I kept going back to look at where the models were placing playuers until I thought a model looked good enough. There is no correct or incorrect answer to this clustering as it kept changing as I was tunign the model with variables. But in the end I was a ble to land on a cluster that I thought was prettu good. 

We first have the facilitators. These are the players with a high basketball IQ and can see plays happening before they happen. In addition, these types of players are typically masters of the half court set offense and they usually know the correct spots for each player on the court. It was not by coincidence that a lot of point gaurds or players with good assist percentages got placed in this catagory. 

Some Examples of facilitaors include Chris Paul, Ben Simmons, Kemba Walker and Darius Garlang.

<p align="center">
   <img src="ChrisPaul.png" width="250" > <img src="BenSimmons.png" width="250" > <img src="KembaWalker.png" width="250" > <img src="DariusGarland.png" width="250" >
</p>

Next Up we have the Big Men. This is typically a tall and pysical low post player that is good with good with offensive and defensive rebounds. When someone is referring to the big man on a basketball team, they are usually referring to either the power forward or center.

Some examples of the Big Men include Nikola Vucevic, Kristaps Porzingis, Kar-Anothony Towns and Joel Embied

We then get tot eh shooters who are exacty what they sound like. High shooting rates with good finished percentages. A shooter can not be described by position as easily as a big man and a faciliator, there can be and are many power forwads that are considered shooters. 

Some example of shooters include Kyle Korver, Duncan Robinson, Joe Harris and Gordan Hayword.

We alsol have a misselanious catitgory that include a lot of players that either dont match any of the other classifications. What I found was that a lot of these players were placed in this catagory because they did not have enough time played to describe there playing style correctly. For example there was a player that had a 100% shooting percentage or 0 % APG. This was due to the fact that they did not have enough stats to be classfied properly. I had to adjust the variables and the k-means parameters to cluster these players out.

Finially We have the al arounds players. These are the players that usually do everything, and a lot of the all-star players get catogorized in this catagory.

Some example of the all-ropund players include Lebron James, Nikola Jokic, Jason Tatum and Kawaii Lenord.

    
    



## Model

## Contact Information

**Email:** samruthv@gmail.com   
**LinkedIn:** https://www.linkedin.com/in/samruthv/

