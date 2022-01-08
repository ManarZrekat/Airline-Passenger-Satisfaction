# Airline-Passenger-Satisfaction

The data we received contained airline passenger satisfaction survey, which includes the factors that affect the passenger
satisfaction. To analyze the data and find out which factors contribute the most into the passenger satisfaction we at first
divided the data into 4 parts:

-categorical features, numerical features, Ratings (features that are represented by a score from 1 to 5), target(satisfaction).

We displayed all the features using a correlation matrix to see which features are correlated and which are not, and
considered any two features with a correlation score higher than 0.55 to be correlated, like for example:

Seat comfort is highly correlated with both inflight service and food & drinks.

We then displayed the data using bar charts and histograms to get a better understanding of the data and the features. From
those graphs we concluded that satisfied passengers gave high ratings to those factors:

- cleanliness, leg room service, inflight entertainment , on-board service, seat comfort, online boarding, Baggage handling.


# Preprocessing The Data

To work on that data and perform clustering/classifications we needed to make some changes on the data
-Normalizing and Scaling the numerical features using MinMaxScaler.
-Encoding the categorical features into numerical values to run the clustering/classification models using
OneHotEncoder.
-We dropped irrelevant columns like id and Unnamed: 0 since they contribute nothing to the data.

# Clustering and visualizing models

To cluster the data, we used Kmeans algorithm from the sklearn library.

At first, we performed the clustering on two clusters since satisfaction has two values:

- Satisfied.

- Neutral or dissatisfied.

We used PCA, t-SNE and SOM to visualize the clustering results, to reduce the dimensionality of
the data, since we have many dimensions, we used those models, to try to describe the data, and
simply find a pattern for clustered data.

We then applied the k-elbow method on the train data to get the optimal number of cluster, which turned
out to be 8.

Using 8 cluster, we ran the kmeans model again to analyze the data furthermore and conclude which are
the features that contribute the most into the passenger satisfaction.

After analyzing the clustering results, we got into the conclusion that those five features contributed the
most into the passenger satisfaction

Inflight entertainment, Inflight service, Food and drinks, seat comfort and cleanliness.

We then grouped the features we thought didn’t contribute into the satisfaction which are:

'Departure/Arrival time convenient’, 'Ease of Online booking’ and 'Gate location'

after analyzing the results, we got into the conclusion that we were right, and the results didn’t change
that much.


# Classification

 We ran those 4 classification algorithms on the training and test data:
- ADABOOST
- Random Forest
- Neural nets
- SGD
-CatBoost

To display the results of each model, we used correlation matrix.
CatBoost gave us the best accuracy which is 95%.

# Predicting satisfaction Using regressors and by
creating a new label.

To create the new feature we, we used the feature importance method on Adaboost classifier
since it gave us the best accuracy and chose to group the top 5 most important features into a
new feature according to classifier results.

We got that - Inflight Wi-Fi service, Online boarding, Seat comfort, Leg room service, Inflight
service are top 5, we grouped their values and computed their mean as a new label.

We chose to run those 3 Regressor models on our new data

Linear Regression, PLS Regression and Decision Tree Regressor.

Once on the data without the top 5 features and once with those 5 features included and
compared the results.

# Conclusion

It was very interesting to see the results of our work on the data, running the classification,
regression models we mentioned before and after clustering, we concluded by the end that
those factors contribute the most into the passenger satisfaction:

1- Ease of online booking

2- Inflight entertainment

3- Inflight Wi-Fi service

4- Customer Type

5- Type of travel
