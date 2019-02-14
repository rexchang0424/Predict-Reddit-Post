# Subreddit API - League of Legends & Rainbow Six Siege
##### created by: Rex Chang

#### Contents:
- [Executive Summary & Problem Statment](#Executive-Summary)
- [Brief Data Description](#Libraries%2Fmodel-used%3A)
- [Conclusion](#Conclusion%3A)

## Executive Summary
---

Video game culture is a worldwide new media subculture formed by video games. As computer and video games have exponentially increased in popularity over time, they have had a significant influence on popular culture. Video game culture has also evolved over time hand in hand with internet culture as well as the increasing popularity of mobile games. gamers find themselves in growing social networks. Gaming can both be entertainment as well as competition, as a new trend known as electronic sports is becoming more widely accepted.



## Problem Statement:
---
I am a data scientist from Discord. Discord is a widely used gaming chatting platform, where gamers create their own channel and discuss topics about a specific game. There is a discord channel where player can ask any questions. 

my objective is to determine which channel to direct the player to, by the used of their words. I will be looking at two specific game, League of Legends and Rainbow 6. Because these two games have to most active community and the play style of the two games are very different. I will obtain subreddit API from both game and apply the data to two classifier regression models: Logistic Regression and Random Forest Classifier. Then I will observe top ten less/most likely words that player will mentioned in these two games.

---
## Libraries/model used:
- pandas
- numpy
- scikit-learn
- Logistic Regression
- Random Forest Classifier
- Regex

### What kind of data are we dealing with ?
I've gathered API from each subreddit in two categories, submission and comment. For each submissions and comments I grabbed 10,000 posts. Therefore, I have total of 40,000 posts in total. I eliminated the words that mentioned the game itself, also the characters name in game to make my data pure. 

- League of Legends Champion's name can be found [Here](https://na.leagueoflegends.com/en/game-info/champions/)
- Rainbow Six Operator's name can be found [Here](https://rainbow6.ubisoft.com/siege/en-us/game-info/operators.aspx)
- League of Legends Subreddit [Here](https://www.reddit.com/r/leagueoflegends/)
- Rainbow Six Siege Subreddit [Here](https://www.reddit.com/r/rainbow6/)



                                           Most Important to Positive Class
|feature | importance |
| --- | --- |
| casual | 127.246297 |
|console| 120.084069 |
|round |	82.008072 |
|gun |	66.207453 |
|pc |	48.702317 |
|renown |	46.944932 |
|ops |	41.153432 |
|map |	36.770953 |
|elite |	34.952138 |
|weapon |	34.596425 |

Let's take a closer look of the first three.

- By looking at the highest, which is **casual**. This means if the word **causal** appear in the context like submissions or comments, this context are approximately 125 times more likely to be our positive class (talking about rainbow six). After researching, this is true. Because causal is considered as one of the game mode in Rainbow Six. 

- Secondly, **Console**. Players can play rainbow six either on console or pc, comparing with league of legends. League of legends only offer on PC only. So comparing with our negative class, the word **Console** is approximately 120 times more likely to appear in Rainbow Six instead.

- Third, **Round**. In Rainbow six you'll be assigned into two sides. Attack side or Defense side. So after a **round** is over, they will switch sides. Therefore, the player that used the word **round** in the context will be approximately 80 time more likely to fall to our positive class. Whereas, League of Legends doesn't have rounds. It's either one game or the other. 


                                           Least Important to Positive Class
|feature | importance |
| --- | --- |
| euw |	0.005857 |
| client |	0.008184 |
| iron |	0.008999 |
| ult |	0.009216 |
| lane |	0.011712 |
| adc |	0.012898 |
| pyke |	0.016884 |
| lp |	0.017890 |
| rp |	0.018140 |
| jungle |	0.018699 |

Let's take a closer look of the first three.

- By looking at the lowest, which is **euw**. This means if the word **euw** appeared in the context like submissions or comments, this context are approximately 0.0055 times more likely(which is less likely) to be our positive class (rainbow six). euw means lagging, which league of legends player likes to say. 

- Secondly, **client**. In the league of legends subreddit, they often discuss client updates a lot. comparing with rainbow six, they don't describe the updates as client update, instead they say path updates. 

- Third, **iron**. In League of legends, they differentiate the ability of player by divisions of badges. The badge's material demonstrate how good the player are. Iron, Bronze, Silver, Gold, Platinum, Diamond, Master, Grandmaster and Challenger. So, people in the league of legends community like to call other player as iron, meaning they're bad.

---

## Conclusion:
In conclusion, after refining our models over time, and the use of Regex, StopWords, tfidf, lemmatize, and grid search. With the final decision of using Logistic Regression model. I have concluded the ten words that are most likely describing rainbow six and ten words that are most likely describing league of legends. Now we can predict which game is the player asking about, then redirect the player to the correct Discord channel to get his/her question answered.

My recommendation for this case is, if given more time I can gather more information from more games to apply to my model. This will not only increase the efficiency on direct player to the correct channel. but also, allow more player to use our platform.


