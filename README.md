# Yelp Maps
Introduction
In this project, a visualization of restaurant ratings using machine learning and the Yelp academic dataset is created. In this visualization, Berkeley is segmented into regions, where each region is shaded by the predicted rating of the closest restaurant (yellow is 5 stars, blue is 1 star). Specifically, the visualization I will be constructing is a Voronoi diagram.



In the map created by the visualization, each dot represents a restaurant. The color of the dot is determined by the restaurant's location. For example, downtown restaurants are colored green. The user that generated this map has a strong preference for Southside restaurants, and so the southern regions are colored yellow.

This project uses concepts from Sections 2.1, 2.2, 2.3, and 2.4.3 of Composing Programs. It also introduces techniques and concepts from machine learning, a growing field at the intersection of computer science and statistics that analyzes data to find patterns and make predictions.

abstractions.py: Data abstractions used in the project
recommend.py: Machine learning algorithms and data processing
utils.py: Utility functions for data processing
ucb.py: Utility functions for CS 61A
data: A directory of Yelp users, restaurants, and reviews
ok: The autograder
proj2.ok: The ok configuration file
tests: A directory of tests used by ok
users: A directory of user files
visualize: A directory of tools for drawing the final visualization


# K-means
Restaurants tend to appear in clusters (e.g. Southside restaurants, Gourmet Ghetto). In this phase, we will devise a way to group together restaurants that are close to each other.

The k-means algorithm is a method for discovering the centers of clusters. It is called an unsupervised learning method because the algorithm is not told what the correct clusters are; it must infer the clusters from the data alone.

The k-means algorithm finds k centroids within a dataset that each correspond to a cluster of inputs. To do so, k-means begins by choosing k centroids at random, then alternates between the following two steps:

Group the restaurants into clusters, where each cluster contains all restaurants that are closest to the same centroid.
Compute a new centroid (average position) for each new cluster.

#Glossary
Throughout the project, one will encounter the following terminology. 

location: A pair containing latitude and longitude. Note that this is not a data abstraction, so we can assume its implementation is a two-element sequence.
centroid: A location (see above) that represents the center of a cluster
restaurant: A restaurant data abstraction, as defined in abstractions.py
cluster: A list of restaurants grouped around a centroid
user: A user data abstraction, as defined in abstractions.py
review: A review data abstraction, as defined in abstractions.py
feature function: A single-argument function that takes a restaurant and returns a number, such as its mean rating or price

