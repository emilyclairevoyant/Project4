**Movie Recommendation System**

**_Introduction_**

In today's entertainment landscape, movies profoundly influence our perspectives and emotions. However, the overwhelming variety of films across platforms, languages, and genres often makes choosing what to watch a challenge for users and a potential revenue risk for streaming platforms. This highlights the critical role of intelligent movie recommendation systems in enhancing user satisfaction and driving business success.

Our project explores Machine Learning-based Recommender Systems to offer personalized movie suggestions tailored to individual preferences. By analyzing user profiles, movie attributes (e.g., genre ratings) we create a dynamic, intuitive movie discovery experience.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Recommendation Systems_**

_Collaborative Filtering_

Collaborative filtering uses user behavior patterns and other users' feedback to make recommendations. In our model:

Recommendations are based on ratings and feedback from users with similar behavior.
This approach personalizes recommendations using patterns derived from user-item interactions.

![https://miro.medium.com/v2/resize:fit:1096/format:webp/1*pv6CDVqPgITYi_Nr0RygUw.png](https://miro.medium.com/v2/resize:fit:1096/format:webp/1*pv6CDVqPgITYi_Nr0RygUw.png)

_Content-Based Filtering_

Content-based filtering focuses on movie attributes such as genres. It 
recommends movies with similar attributes to those the user has already enjoyed.
Relies on analyzing the specific features of the movies rather than user behavior.

![https://miro.medium.com/v2/resize:fit:1400/format:webp/1*dsuGJVJSqhhhNySFnt7EVw.png](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*dsuGJVJSqhhhNySFnt7EVw.png)



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Data Sets_**

We utilized the MovieLens dataset to develop and evaluate our models:

* Small Dataset: 610 users, 9,724 movies.

* Large Dataset: 200,948 users, 87,585 movies.

The system scales across both datasets, offering detailed insights and adaptability.

To have the models function appropriately please make sure to access the data of your choice (https://grouplens.org/datasets/movielens/) and create a python file called 
"mongo_credentials.py" with the contents stating "connection_string = "enter your string here".


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Tools and Technologies_**

Ensure the following tools and libraries are installed for seamless functionality:

* Programming: Python (Jupyter Notebook)

* Database: MongoDB Atlas

* Libraries: Pandas, PyMongo, Scikit-learn, Fuzzywuzzy, Pprint, Numpy, Pathlib, Matplotlib, Datetime, TensorFlow, Collections, Itertools

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Models Overview_**

_KNN Recommender_

* Approach: Collaborative filtering

* Implementation: Uses a utility matrix (scipy.sparse.csr_matrix) to analyze user-item interactions.

* Features:

  * Generates recommendations using cosine similarity.

  * Filters noise by including users and movies with a minimum number of interactions.

* Evaluation: RMSE and MAE on training and test datasets ensure predictive accuracy.
  

_Cosine Recommender with Rating Predictor_

* Approach: Content-based filtering combined with collaborative filtering.

* Features:

  * Recommends movies using cosine similarity of genres.

  * Predicts user ratings with Truncated Singular Value Decomposition (SVD).

* Evaluation: Achieved low MAE and RMSE scores for rating predictions.
  

_DBSCAN Clustering and Neural Network_

* Approach: Unsupervised learning for clustering and neural networks for prediction.

* Features:

  * Groups users based on ratings and genre preferences.

  * Neural network predicts average ratings for specific genres.

* Evaluation: Achieved reasonable MAE (~0.25) and R-squared (0.59) scores, highlighting areas for improvement.
  

_Franchise SVD_

* Approach: SVD for franchise-specific rating predictions.

* Features:

  * Predicts ratings for future films in a series.

* Challenges: Limited data due to small franchise sample sizes impacts prediction accuracy.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Model Performance Analysis_**

_Strengths_

* KNN: Simple, interpretable, and highly personalized recommendations.

* Cosine Recommender: Precise, genre-based recommendations with collaborative rating prediction.

* DBSCAN: Robust clustering for irregular data and outlier detection.

* Franchise SVD: Predicts future franchise film ratings, useful for production insights.

_Challenges_

* KNN: Suffers from the cold start problem and limited scalability.

* Cosine Recommender: Memory-intensive and requires manual evaluation for relevance.

* DBSCAN: Sensitive to parameter choices; performance highly dependent on tuning.

* Franchise SVD: Small datasets reduce accuracy and relevance to box office success.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Conclusion_**

This project combines KNN, SVD, DBSCAN, and neural networks to deliver a multi-faceted recommendation system. By addressing the cold-start problem with genre-based cosine similarity and leveraging collaborative and content-based filtering, the system provides robust personalized recommendations. Future work will focus on integrating strengths across models to improve scalability, precision, and user-centric design.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**_Credits_**

Dataset:

F. Maxwell Harper and Joseph A. Konstan. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems, 5(4): 19:1–19:19 (2015). DOI:10.1145/2827872.
