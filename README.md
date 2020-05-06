# Sparkify churn prediction with PySpark and SparkML


## Project Overview
Sparkify is a streaming service that offers music, similarly to other currently known services such as Spotify. As a user, you can interact with the service and choose your favourite artists, songs, create playlists or add friends. Any time you like, you can give a thumbs up or down. You may decide whether you are happy with the free subscription (and bear the reappearing advertisements) or you are ready to pay for it. You can change your subscription plan any time you want, upgrading or downgrading multiple times. Finally, you can decide to completely quit the app. But what makes you want to do it?
This is the question I want to focus on in this article. I want to bring closer to you my approach to and results of a project where I aim at predicting if and why any user would be likely to churn and quit the service provided by Sparkify.
Sparkify is a company just like any other, just it is fictitious. Consequently, the dataset consists of simulated logs of user interaction with the service within an observation period. The project itself is a part of the Data Science Nanodegree, organized by Udacity, who provided the dataset.
How to approach this problem, essential from the business point of view? Let’s find out!

As stated, the goal is to be able to predict whether a user is about to churn the service and possibly have a deeper insight on what it depends on. Successful prediction would be the first step to keep the customer, as it would prompt an action in form of sending some incentives, analysing discouraging factors, sending personal recommendations and similar. It is advantageous to have customers with paid subscription, however the real problem is to have a customer quit (and not being able to address her/him as a customer anymore), so churning is defined here as quitting the service all together.

The entire development process (data exploration, feature engineering, model selection) is conducted on a subset (1/100) of the full dataset. Model selected after this process can be further trained and tested on the full dataset. Because of its size it cannot be processed locally and has to be processed in the cloud, for example on the EMR cluster (Elastic MapReduce). That is out of scope of this development notebook, yet the logic stays the same.
Because of that, the project is realised utilising advantages of Apache Spark distributed computing framework. In particular, its python API, PySpark and SparkML are used during the development process.

To this end, I divide the strategy for solving the problem into the following steps that I comment on in the next sections:

1. Data exploration:
* load the data
* deal with incomplete data, identify outliers
* visualize and understand correlations
2. Feature engineering:
* transform the data into a dataset of one sample record per user, aggregating features and performing statistics on them
* decide what features to take or what potential new features to engineer
* define the target response variable for training
3. Modeling and evaluation:
* define objective in mathematical terms
* create proper metric to track performance
* come up with suitable models and train them
* evaluate various models according to the chosen metrics and decide for the most promising one
* refine the model


## Minimal requirements:
* python 3.x,
* numpy 1.12.1, 
* pandas 0.23.3, 
* pyspark 2.4.3,
* seaborn 0.8.1,
* matplotlib 2.1.0.


## Installation:
Clone the following repository:
```
git clone https://github.com/rrstal/dsnd-sparkify-churn-prediction.git
```

## Software description & results:

* `sparkify.ipynb` - jupyter notebook with the code for the whole development process of the solution: data analysis, feature engineering, modelling. Contains commentaries, code, visualizations and results. For more in depth description, please refer to [this article in Medium](https://medium.com/@raimateus/sparkify-churn-prediction-data-science-udacity-nanodegree-4871c0c79c65).


## Acknowledgements
All the credits for organising the course, project and finally providing the simulated dataset go to Udacity.