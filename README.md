# Inventory Boosted Trees

Using customer shopping data to determine shopping trends. The data is highly imbalanced so an implementation of Boosted Trees was used to optimize random forest classification system.

Observations:
The difference between various types of trees is as follows
* As expected the Bagging model uses subsamples so it has only 11333 samples.
* The simple tree without any kind of boosting or bagging is the only one that starts with a low gini value (less than 0.1). The other two models actually have first node gini of 0.5
* The balanced subsample version of the classifier (tree_cbrf) has several leaves at 3rd level. These are mainly associated with InsessionView, MaxPrice classes.
* The 
