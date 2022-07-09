# ⛩️ Content Based & Collaborative Filtering - Anime Recommender System ⛩️
## (ฅ^•ﻌ•^ฅ) 


## Introduction

#### This notebook is written and illustrated by an Ironhack student - Dory, a young data enthusiast who seeks recognition from her peers and dreams of becoming a Data Scientist. With the help of Machine Learning, StackOverflow, Google and her friends from her class, Dory wants to become a Hokage and create an anime recommender.

<img src="https://media.giphy.com/media/Nzz86dByLtYTS/giphy.gif" width="750" align="center">

#### The main goal of this project is to use NLP techniques to analyze anime synopsis of the anime catalogue, user rating data and build an anime recommender system.  
#### This notebook uses 3 datasets:
* `anime` : contain general information of every anime (17.562 different anime) like genre, stats, studio, etc. This file have the following columns:
* * MAL_ID: MyAnimelist ID of the anime. (e.g. 1)
* * Name: full name of the anime. (e.g. Cowboy Bebop)
* * Score: average score of the anime given from all users in MyAnimelist database. (e.g. 8.78)
* * Genres: comma separated list of genres for this anime. (e.g. Action, Adventure, Comedy, Drama, Sci-Fi, Space)
* * English name: full name in english of the anime. (e.g. Cowboy Bebop)
* * Japanese name: full name in japanses of the anime. (e.g. カウボーイビバップ)
* * Type: TV, movie, OVA, etc. (e.g. TV)
* * Episodes': number of chapters. (e.g. 26)
* * Aired: broadcast date. (e.g. Apr 3, 1998 to Apr 24, 1999)
* * Premiered: season premiere. (e.g. Spring 1998)
* * Producers: comma separated list of produducers (e.g. Bandai Visual)
* * Licensors: comma separated list of licensors (e.g. Funimation, Bandai Entertainment)
* * Studios: comma separated list of studios (e.g. Sunrise)
* * Source: Manga, Light novel, Book, etc. (e.g Original)
* * Duration: duration of the anime per episode (e.g 24 min. per ep.)
* * Rating: age rate (e.g. R - 17+ (violence & profanity))
* * Ranked: position based in the score. (e.g 28)
* * Popularity: position based in the the number of users who have added the anime to their list. (e.g 39)
* * Members: number of community members that are in this anime's "group". (e.g. 1251960)
* * Favorites: number of users who have the anime as "favorites". (e.g. 61,971)
* * Watching: number of users who are watching the anime. (e.g. 105808)
* * Completed: number of users who have complete the anime. (e.g. 718161)
* * On-Hold: number of users who have the anime on Hold. (e.g. 71513)
* * Dropped: number of users who have dropped the anime. (e.g. 26678)
* * Plan to Watch': number of users who plan to watch the anime. (e.g. 329800)
* * Score-10': number of users who scored 10. (e.g. 229170)
* * Score-9': number of users who scored 9. (e.g. 182126)
* * Score-8': number of users who scored 8. (e.g. 131625)
* * Score-7': number of users who scored 7. (e.g. 62330)
* * Score-6': number of users who scored 6. (e.g. 20688)
* * Score-5': number of users who scored 5. (e.g. 8904)
* * Score-4': number of users who scored 4. (e.g. 3184)
* * Score-3': number of users who scored 3. (e.g. 1357)
* * Score-2': number of users who scored 2. (e.g. 741)
* * Score-1': number of users who scored 1. (e.g. 1580)
* `rating` : This dataset contains 57 Million ratings applied to 16.872 animes by 310.059 users. This file have the following columns:
* * user_id: non identifiable randomly generated user id.
* * anime_id: MyAnimelist ID of the anime that this user has rated.
* * rating: rating that this user has assigned.
* `synopsis` : contains the synopsis (description) of every anime.
* * mal_id : MyAnimelist ID of the anime.
* * name : the name of the anime
* * score : average score of the anime given from all users in MyAnimelist database
* * genres: comma separated list of genres for this anime
* * synopsis : the synopsis of every  anime


### Table of Contents
1. [Introduction](#introduction)
    1. [Datasets information](#this-notebook-has-3-datasets)
2. [`Anime` dataset](#anime-dataset)
    1. [Cleaning](#cleaning)
    2. [Treating the null values](#treating-the-null-values)
3. [`Rating` dataset](#rating-dataset)
4. [`Synopsis` dataset](#animewithsynopsis-dataset)
    1. [Cleaning](#cleaning-the-columns)
    2. [NLP](#nlp)
    3. [Clustering](#clustering)
5. [The Recommender system](#the-recommender)
