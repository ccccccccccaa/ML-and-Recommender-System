# **Recommendation System Algorithms from Scratch**

This project implements and evaluates several common collaborative filtering algorithms for building a recommendation system. The goal is to predict user ratings for items based on past rating data. All algorithms are built from the ground up using Python, NumPy, and Pandas.

## **Dataset**

The project uses the **MovieLens 100k dataset**, which contains 100,000 ratings from 943 users on 1682 movies.

You can download the dataset from my repo or the GroupLens website: [MovieLens 100k Dataset](https://grouplens.org/datasets/movielens/100k/)

For this project to run correctly, please download the ml-100k.zip file, extract it, and ensure the u.data file is located in a folder named ml-100k within the project's root directory.

## **Algorithms Implemented**

The following recommendation algorithms have been implemented and compared:

1. **User-Average:** A simple baseline model that predicts a user's rating for any item as the average of that user's historical ratings.  
2. **Item-Average:** Another baseline model that predicts the rating for an item as the average of all ratings it has received from all users.  
3. **User-Based k-Nearest Neighbors (k-NN) Collaborative Filtering:** This model finds the *k* most similar users to a target user and predicts ratings based on a weighted average of their ratings. Similarity is calculated using the Pearson correlation coefficient with significance weighting.  
4. **Item-Based k-Nearest Neighbors (k-NN) Collaborative Filtering:** This model calculates the similarity between items and predicts a user's rating for an item based on the ratings they gave to the *k* most similar items. Similarity is also calculated using the Pearson correlation coefficient with significance weighting.  
5. **Hybrid k-NN Collaborative Filtering:** A model that combines the predictions from both the User-Based and Item-Based k-NN models using a weighted average to improve prediction accuracy.

## **Requirements**

To run this project, you'll need Python 3 and the following libraries:

* pandas  
* numpy  
* scikit-learn  
* jupyter

You can install them using pip:

pip install pandas numpy scikit-learn jupyterlab

## **How to Run**

1. **Clone the repository:**  
   git clone \<your-repository-url\>  
   cd \<your-repository-directory\>

2. **Download the dataset** as described above and place it in the ml-100k folder.  
3. **Launch Jupyter Notebook or JupyterLab:**  
   jupyter lab

4. Open and run the Assignment3\_framework.ipynb notebook to see the implementation and results.

## **Performance Results**

The models were evaluated using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) on a held-out test set. Lower values indicate better performance.

| Model | MAE | RMSE |
| :---- | :---- | :---- |
| 1\. User-Average | 0.8259 | 1.0311 |
| 2\. Item-Average | 0.7961 | 1.0013 |
| 3\. User-Based k-NN (k=50) | 0.7399 | 0.9550 |
| 4\. Item-Based k-NN (k=50) | 0.7250 | 0.9326 |
| 5\. Hybrid k-NN (User-Based \+ Item-Based) | **0.7189** | **0.9231** |

As shown in the table, the Hybrid k-NN model achieved the best performance by combining the strengths of both user-based and item-based collaborative filtering approaches.
