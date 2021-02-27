# Simplified decision trees generation for rule-based inference, with CART algorithm
Decision tree based methods are a very powerful machine learning technique, particularly for tabular data.
They can generate decision trees for you, based on your data, in an iterative fashion.  
For tabular data (meaning not images, not time series,not language... Only plain regular excel-like tables with columns, every line being independant from each other and containing several predictor variables), decision tree based machine learning algorithms are in fact performing at state of the art level (with algorithms such as XGBoost, LGBM).  
This scikit-learn page is interesting, to understand tree-based models : https://scikit-learn.org/stable/modules/tree.html  

However, the most performing decision tree algorithms generate very complex trees that can be very, very deep, and you can have multiple trees based on residual errors of former ones. It is impossible for a human to understand such trees in a global way.  

In some cases, it is useful to have some human-interpretable models, in order to :  

- Check if you can trust the algorithm
- Be able to justify your choices to regulators (typically financial regulators in credit risk problems)
- Discover business rules from the data and use them to better approach your customers
- Decrease maintenance efforts by using simpler (but less performing), close to business ruled-based models that will be more robust to new kind of data than more complex (though more performing) machine learning models  

There are many techniques for human-interpretability / explainability of machine learning models, including LIME or SHAPLEY : those techniques are interesting because they allow you to maintain your model complexity (which means keep your level of performance) and still explain what's happening. But even with LIME or SHAPLEY it can still sometimes be difficult to explain some decisions, and you still have model maintenance / retraining issue.  

In the following notebook, we'll see a much more simple technique, based on DecisionTreeClassifier from scikit-learn (CART algorithm) + some additionnal code we wrote, in order to generate simple, human-understandable rules from data. To generate those rules though, we'll have to sacrifice performance (more precisely this means that our simple rule-based model will only be able to predict a subsample of instances, not all of them). We want those rules to be simple (not more than 2 criterias), precise (as in good precision score). Exhaustivity and recall will not at all be our priority.  
[See notebook](https://www.kaggle.com/franoisboyer/simplified-decision-trees)
