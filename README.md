**Movie Recommendation System**

This project implements a movie recommendation system using a weighted rating formula inspired by IMDB. The objective is to rank movies based on a combination of their popularity (vote count) and quality (vote average), ensuring that movies with a small number of votes don’t unfairly rank higher due to their high average rating.

**How It Works**

Data and Metrics Used:

vote_count (v): The total number of votes a movie has received.
vote_average (R): The average rating of the movie.
C: The mean vote average across all movies (a global metric to standardize scores).
m: The minimum number of votes required to be considered for the ranking (threshold to filter out less popular movies).

Weighted Rating Formula: The system uses the weighted rating formula to calculate a score for each movie:

Movies with higher vote_count contribute more to the final score (v/(v+m)).
The global average C contributes more to movies with fewer votes (m/(v+m)).
This balances popularity and quality, favoring movies that are both highly rated and widely rated.
Implementation:

The weighted rating formula is applied to each movie using apply() from the Pandas library.
The movies are then sorted by their calculated score in descending order.
The top 15 movies are displayed based on this score.
Output:

The top movies are shown with their:
Title
Vote count
Vote average
Weighted score

**Why This Method?**

Ensures that a small number of high ratings don’t artificially boost the ranking of less popular movies.
Rewards movies that have a strong combination of quality and popularity.

**How to Use This System**

The dataset should include title, vote_count, and vote_average columns.
Adjust m (minimum votes) based on the dataset size and the desired threshold for popular movies.
The output provides a ranked list of recommended movies, which can be further used in a recommendation application.

**Enhancements**

Add filtering options by genres, release years, or language.
Integrate collaborative filtering or content-based filtering for personalized recommendations.
Deploy the system as a web or mobile application using frameworks like Flask or React.
