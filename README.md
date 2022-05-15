# Udacity-Recommendations-with-IBM
- [Project Goal](#Project-Goal)
- [The Tasks](#Tasks)
- [Installation](#Installation)
- [Results](#Results)
- [Next Steps](#Next)
- [Licensing, Authors, Acknowledgements](#License)

## Project Goal <a name="Project-Goal"></a>
The goal of this project is to build a recommend system to recommend articles to users on IBM Watson Studio platform

**Background:** In this project, I will build a recommendation system to provide articles I think users will likely to read by explore the interactions the users have with articles on the IBM Watson Studio platform. Ultimately, users are welcomed with a dashboard displaying articles recommended.


## The Tasks <a name="Tasks"></a>
### I. Exploratory Data Analysis (EDA) 
- 2 given dataframes: one df contains the interactions between user and articles, one df contains articles' information
- Explore the user-articles interactions

### II. Ranked Based Recommendations 
- The first approach is to recommend the most popular articles based on the number of interactions
- There is no rating on articles, thus it is assumed that articles with most interactions (most viewed) are amongst the popular. 

### III. User-User Based Collaborative Filtering
- The second approach is more personalized in which I will find users that are similar to each other in terms of the articles they've interacted with.
- Users are similar to each other may share the same topics of interest and have read several same articles.

### IV. Matrix Factorization
- Use Single Value Decomposition (SVD) to build a matrix decomposition
- Evaluate how well the model can predict user-article interaction

## Installation <a name="Installation"></a>
The following packages and versions are used in this jupyter notebook. Any newer versions should work. 
| Package  | Version |
| ------------- | ------------- |
| Python  | 3.8.5  |
| Numpy   | 1.19.2 |
| Matplotlib | 3.3.2|


## Resutls <a name="Results"></a>
### Discussion 
- The accuracy curve for the test set is the inverse of it for the train set. This indicates that we overfit during training by increasing the number of latent features, which shows poor result in test set.
- By comparing the accuracy of train and test set, we should keep it simple by using fewer latent features (~ 200 max)
- Besides, we have a very small dataset with only 20 users, whom we are able to give the recommendation, to work with. Any recommendation methods seem to have its own drawback to meet the expectation at this moment.

### Suggestion
- Collect more data from the users and their interaction with the articles to build better recommendation systems
- Retrain SVD
- Perform A/B testing to compare each recommendation method to each other, and to a combination one.
- Implement some type of ratings to understand the users preference (type of articles they most interact with) as well as to learn their feedback on the current recommendation (like/dislike)

## Next Steps <a name="Next"></a>
I will work on the following steps to improve and complete the recommendation system.
- Build **content based** recommendations using NLP
- Make a Flask app

![dashboard](Dashboard.PNG)
Figure 1. An example of the dashboard made with Flask

## Licensing, Authors, Acknowledgements <a name="License"></a>
* IBM for providing the datasets and project goal
* [Udacity](https://www.udacity.com/) for instructions
* Author: [Nguyen Pham](https://github.com/Az-otrope)

