# Inventory Prediction Using Decision Trees

Using customer shopping data to determine shopping trends. The data is highly imbalanced so an implementation of Boosted Trees was used to optimize random forest classification system.

Observations:
The difference between various types of trees is as follows,
* The RF tree has low recall.
* As expected the Bagging model uses subsamples so it has only 11333 samples.
* In terms of importance of features the trees show that the first main feature of importance are NumViews. The bagged model uses interaction time as an important variable
* The importance of second level features varies according to models.
  * Simple RF has maxPrice, NumCart and interactionTime as main features
  * Boosted tree places more importance on maxPrice and InsessionView
  * Bagged model has MaxPrice and NumCart as most important values
* The boosted model reaches gini value of zero in several instances at only 3rd level.

Based on all the models I would recommend that the most important value to optimize is the Number of items that are viewed. Followed by the price. It seems like that low price items get more views and also end up in cart a lot of times. Basically getting traffic on the website and trying to maximize views of items on the website and then placing lower cost items more often can lead to increased purchase rates.


## Other Observations
*The simple tree without any kind of boosting or bagging is the only one that starts with a low gini value (less than 0.1). The other two models actually have first node gini of 0.5
* The balanced subsample version of the classifier (tree_cbrf) has several leaves at 3rd level. These are mainly associated with InsessionView, MaxPrice classes.

!['tree.png'](https://github.com/taimur1871/inventory_boosted_trees/blob/main/optimized_tree_brf.png)
