##  Introduction


Machine Learning has a handful number of Classification and Regression Algorithms. All these intend to solve the same problem but each algorithm stands out with its methodology. Machine Learning has adapted to address a wide range of real-world problems right from recommendation systems to self-driving cars where each area has its limitations. Decision Trees are one such algorithm used to solve classification and regression problems. 

## Decision Trees
Decision trees are based on tree-like models which help to decide on the process at each leaf node based on probability. Decision trees are white-box models where the predictive outcome can be tracked. It is also very similar to how we make decisions in real life, deciding on a series of questions.


<img style="display: block;  margin-left: auto;  margin-right: auto;  width: 50%;" src="https://cdn2.hubspot.net/hubfs/4145950/Imported_Blog_Media/tree1.png" width="400" height="400" />

### Classification with Decision Trees

Essentially every node in a decision tree will represent a validation of some condition. Every node will branch out into two partitions based on the node validation for a binary tree. If we have more than two partitions it's called a multiway decision tree. All the algorithm does is divide the dataset into multiple sub-datasets which follow a pattern. Here we will be focussing more on the binary decision tree.

### Regression with Decision Trees

In Regression, the attributes are continuous variables hence decision tree will bucket the range of values into desired classes.
For Example, Age is a variable that has values ranging from 0 - 100. a decision tree will be possibly bucketing them into 0-18, 18-30, 30-55, 55-100 classes. So a decision can be taken at the node and through the respective branch successive nodes are considered.

So now, we understood how a decision tree works. But still, we did not discuss which attribute is prime to be a parent node or the order in which each attribute divides the dataset. Which attribute is used to split the dataset first is the question!

## Homogeneity Measure:

Consider a classification dataset with two labels. Now when a dataset is split over an attribute into two branches and if both datasets now belong to different labels then both datasets are completely homogenous. In a Real-world dataset complete homogeneity is not possible so algorithms will try to achieve the maximum possible homogeneity split.

So we go step-by-step, picking an attribute and splitting the data such that the homogeneity increases after every split and we stop splitting when the resulting leaves are sufficiently homogenous. 

## Techniques for Quantifying Homogeneity

### Gini index
Gini Index, also known as Gini impurity, calculates the amount of probability of a specific feature that is classified incorrectly when selected randomly. It is pure if all the data belongs to the same label and the value of the Gini index lies between 0 to 1

![Image](https://miro.medium.com/max/417/1*QF-JeWpQQ86xhRhseHGecg.png)

### Entropy
Entropy is the main concept of this algorithm, which helps determine a feature or attribute that gives maximum information about a class is called Information gain

![Image](https://datascience.foundation/img/pdf_images/understanding_decision_trees_with_python_gini_impurity_2_1.png)

### Information Gain:
The difference in entropy of node and sum of the entropy of all child nodes. Based on the measures the algorithm will split the dataset.

There are few disadvantages of Decision trees they have a strong tendency to overfit the data, which is a serious problem. We need some regularization methods to be taken care. There are two broad strategies to control overfitting in decision trees: truncation and pruning. 

### Truncation: 

Consciously stopping the tree to further branch out at one point in time. This Truncation is done based on Homogeneity Threshold. When homogeneity is greater than the threshold then tree is stopped to grow further

### Pruning:

The tree is allowed to split as maximum as possible then we will decide to ignore the leaves which aren't effective. its generally bottom-top method

Below are the parameters considered for both truncating and pruning
- Threshold (Gini/IG or entropy)
- Maximum features  
- Maximum depth of the tree
- Min samples to split
- Min samples in leaf 

We can increase the accuracy even more and be able to regularize the models better through ensemble methods. An ensemble means a group of things viewed as a whole rather than individually. In ensembles, a collection of models is used to make predictions, rather than individual models. We will use Random Forest which is one of an ensemble technique.

## Random Forest:

Instead of one decision tree in random forest, we generate various tree models and ensemble them. We use Bagging (Bootstrap Aggregating) as an ensemble method. Each Tree is modeled based on a different data sample. Having different features, different training data sample makes random forest more diverse and hence less overfitting.

![Image](https://cdn.corporatefinanceinstitute.com/assets/random-forest.png)
