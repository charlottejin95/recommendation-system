# **Moive Recommendation System using ALS in Spark**
In this notebook, I am using an **Alternating Least Squares (ALS) Matrix Factorization algorithm with Spark APIs** to predict movie ratings for different users, providing movie suggestions based on user historical watches. Using grid search to get optimal hyper-parameters, train the model to propose two user cases of: **provide top 10 movie recommendations for each user** and **find similar movies for each movie**\
\
**Data set** used in the analysis: [MovieLens small dataset](https://grouplens.org/datasets/movielens/latest/)\
\
**Data set summary**: \
This dataset describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service. It contains 100836 ratings and 3683 tag applications across 9742 movies. These data were created by 610 users between March 29, 1996 and September 24, 2018. This dataset was generated on September 26, 2018.

Users were selected at random for inclusion. All selected users had rated at least 20 movies. No demographic information is included. Each user is represented by an id, and no other information is provided.

This data set includes the following files: `links.csv`, `movies.csv`, `ratings.csv` and `tags.csv`.

- **`movies.csv`**: \
Movie information is contained in the file `movies.csv`. Each line of this file after the header row represents one movie, and has the following format: *movieId*, *title*, *genres*. Movie titles are entered manually or imported from <https://www.themoviedb.org/>, including the year of release in parentheses. Genres are a pipe-separated list.

- **`ratings.csv`**:\
All ratings are contained in the file `ratings.csv`. Each line of this file after the header row represents one rating of one movie by one user, and has the following format: *userId*, *movieId*, *rating*, *timestamp*. Ratings are made on a 5-star scale, with half-star increments (0.5 stars - 5.0 stars).Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970.

- **`links.csv`**:
Identifiers that can be used to link to other sources of movie data are contained in the file `links.csv`. Each line of this file after the header row represents one movie, and has the following format: *movieId*, *imdbId*, *tmdbId*.

 - - movieId is an identifier for movies used by <https://movielens.org>.\
 E.g., the movie Toy Story has the link <https://movielens.org/movies/1>.

- - imdbId is an identifier for movies used by <http://www.imdb.com>.\
 E.g., the movie Toy Story has the link <http://www.imdb.com/title/tt0114709/>.

- - tmdbId is an identifier for movies used by <https://www.themoviedb.org>.\
 E.g., the movie Toy Story has the link <https://www.themoviedb.org/movie/862>.

- - Use of the resources listed above is subject to the terms of each provider.

- **`tags.csv`**:\
All tags are contained in the file `tags.csv`. Each line of this file after the header row represents one tag applied to one movie by one user, and has the following format: *userId*, *movieId*, *tag*, *timestamp*. Tags are user-generated metadata about movies. Each tag is typically a single word or short phrase. The meaning, value, and purpose of a particular tag is determined by each user. Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970.
