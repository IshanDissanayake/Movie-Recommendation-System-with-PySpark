# Movie-Recommendation-System-with-PySpark
Welcome to the Movie Recommendation System!

This project utilizes the `MovieLens 1M dataset` to build a collaborative filtering-based recommendation model, leveraging the power of `Apache Spark` for distributed data processing and machine learning. With `Spark MLlib`, this system is designed to provide personalized movie recommendations by analyzing user preferences and historical interactions. By harnessing Apache Spark's scalability and efficiency, this model can handle large-scale datasets, making it suitable for real-world recommendation tasks.

## Dataset
The project uses the [MovieLens 1M Dataset](https://grouplens.org/datasets/movielens/1m/), which contains:

* 1,000,209 movie ratings by 6,040 users on 3,952 movies.
* User demographic information (age, gender, occupation, etc.).
* Movie metadata (genres, release years, etc.).

## Technologies Used
* **PySpark**: For distributed data processing and machine learning.
* **ALS (Alternating Least Squares)**: Collaborative filtering model for recommendation.
* **RegressionEvaluator**: For evaluating model performance.

## Preprocessing
Data preprocessing is a crucial step to ensure model accuracy and efficiency. The following steps were performed:
1. **Data Loading**:
* Loaded and parsed the dataset files.
* Used Spark DataFrames for distributed processing.

2. **Encoding**:
* Used `StringIndexer` to convert categorical columns(genres) into numeric indices.
* Applied `OneHotEncoder` to encode categorical features.

3. **Feature Engineering**:
* Extracted genres from movie metadata using Spark SQL functions.

4. **Pipeline**:
* Built a reusable preprocessing pipeline to streamline transformations.

## Modeling
The recommendation model uses the `ALS (Alternating Least Squares)` algorithm provided by Spark MLlib.

## Evaluation
* **Metric**: The model is evaluated using **Root Mean Squared Error (RMSE)** to measure prediction accuracy.
* **Tool**: Used `RegressionEvaluator` for evaluation.

## Limitations
While the model performs well in providing movie recommendations, it has the following limitations: 

* **Cold Start Problem**: <br>
The model struggles to provide recommendations for new users or movies with insufficient ratings, as ALS relies on collaborative filtering.

* **Feature Limitations**: <br>
The model currently focuses on collaborative filtering and does not consider content-based features such as movie descriptions or reviews.


* **Scalability**: <br>
While PySpark handles large datasets well, additional optimization and resource scaling are required for very large or real-time systems.

## License
This project is licensed under the `MIT License`. See the LICENSE file for details.
