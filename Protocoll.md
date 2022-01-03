# Day 21, 03.01.2022

---
##  __Schedule__
<span style="color:grey">

|Time|Content|
|---|---|
|09:00 - 10:00|Daily Review|
|10:00 - 11:00|Lecture on KNN|
|11:00 - 12:00|Pair Programming|
|12:00 - 13:00|Lunch Break| 
|13:00 - 16:00|Pair Programming|
|16:00 - 16:30|Daily Standup|

---
## Daily Review

* Why to transform data?  
    
  &#8594; The log transformation reduces or removes the skewness of our original data.
    
* When to split data in training and testing?   
    
  &#8594; For pure data analysis there is no need to split. The purpose of splitting into training and test sets is to verify how well would your model perform on unseen data, train the model on training set and verify its performance on the test set.
    
* When RSME and when R^2?  
    
  &#8594; RMSE is preferably used to compare the performance between different regression models. R-Square and Adjusted R-Square are better used to explain the fit of the model. 

---
## Lecture "k-nearest neighbors"

[Slides](https://github.com/neuefische/cgn-ds-21-3-daily-review/blob/main/slides/14_KNN_and_Distance_Metrics.pdf)

  ![KNN](http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1531424125/KNN_final_a1mrv9.png)
 
* Assumption: Birds of a feather flock together. 
* The goal of the KNN algorithm is to find out to which class a datapoint belongs based on the neighbors of these unknown data point.
* KNN is a supervised learning algorithm.
* KNN is a non-parametric Algorithm: no underlying assumption on mapping function.
* Classification based on similarity measures.
* Lazy Algorithm &#8594; needs almost no training.
* Training time is very low **but** prediction time can be very high if there are many data points. 
  
### How it works
1. Load the data
2. Initialize K to your chosen number of neighbors
3. For each example in the data: Calculate the distance between the query example and the current example from the data. Add the distance and the index of the example to an ordered collection
4. Sort the ordered collection of distances and indices from smallest to largest (in ascending order) by the distances
5. Pick the first K entries from the sorted collection
6. Get the labels of the selected K entries
7. If regression, return the **mean** of the K labels
8. If classification, return the **mode** of the K labels

## Hyperparameter
  
### Number of neighbors &#8594; **K**.
  * small **K** &#8594; could lead to **overfitting**.
  * large **K** &#8594; could lead to **underfitting**.
  * how to find the best value for **K** &#8594; To select the K that’s right for your data, we run the KNN algorithm several times with different values of K and choose the K that reduces the number of errors we encounter while maintaining the algorithm’s ability to accurately make predictions when it’s given data it hasn’t seen before.
  

### Distance Metric

The Minkowski distance can be considered as a generalized form of both the Euclidean distance and the Manhattan distance. The Minkowski distance of order p (where p is an integer) between two points X and Y is given by: ![Minkowski](https://lh3.googleusercontent.com/V79X0fFEPsI1_PmepqzJdRLh7wP5-OKY4bZiE6DwWj0ESBZ8lSf2F2tttuMcpJlEKxEodyO_tTD5SG_qhvIhKxfP22Eu2QE0ImZvIh6Ft8nA7GBmqXSDX2Xt3LbUy515---n1Mg1)
  
  * **Euclidean** Distance &#8594; The Euclidean distance between two points is the length of a line segment between the two points.
    * commonly used when data is dense or continuous.
    * Euclidean Distance = L2-norm(Minkowski p=2)
    
  ![Euclidean](https://www.kdnuggets.com/wp-content/uploads/popular-knn-metrics-4.jpg)
  ![Euclidean](https://www.kdnuggets.com/wp-content/uploads/popular-knn-metrics-5.jpg)
  
  
 * **Manhatten** Distance &#8594; The Manhatten distance between two points is the absolute sum of the difference bewteen the x-coordinates and y-coordinates.
   * Used for high dimensional data.
   * Manhatten Distance = L1-norm(Minkowski p=1)
    
  ![Manhatten](https://user-images.githubusercontent.com/94449728/147970460-c696af58-de08-4e6c-82a3-3b128c90925e.png)
  ![Manhatten](https://www.kdnuggets.com/wp-content/uploads/popular-knn-metrics-3.jpg)


## Further Information
  
  Two  interesting articles:
  * [Most Popular Distance Metrics Used in KNN and When to Use Them](https://www.kdnuggets.com/2020/11/most-popular-distance-metrics-knn.html)
  * [KNN - Torwards Data Science](https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761)
  
  Simons links for todays lecture:
  * [Vector subtraction](https://www.youtube.com/watch?v=DXB1PWq8Dg0)
  * [Vector dot product](https://www.khanacademy.org/math/linear-algebra/vectors-and-spaces/dot-cross-products/v/vector-dot-product-and-vector-length)
  * [Vector dot product - geometric interpretation](https://www.mathsisfun.com/algebra/vectors-dot-product.html)





