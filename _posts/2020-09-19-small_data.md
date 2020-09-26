# Can you apply machine learning on small data ?
## We hear a lot about big data, but what about small data ? :)
Sometimes you just don't have the resources or necessary time to gather much data.

I wanted to have an idea if Machine Learning and statistical correlation analysis could have a chance to give results on small data, and how to measure the probability that our model gives good results.

Here's the detailed work :
https://www.kaggle.com/franoisboyer/machine-learning-with-small-dataset

What I can say from this work is :
- Machine Learning can work with as few as 2000 samples in some cases
- Machine Learning gives you a metric to measure if it's working by directly testing your predictions (and we can have an idea from the 2 examples I analyzed, taht it should be around 80% to have good confidence that it's working, and that at 60% you may have low confidence to capture all the effects of features on the variable to predict)  
- What could you do *before gathering your data* to get the best possible estimation of how much samples you would need ?
> Try your best to figure out the expected distribution of data, then sample random data according to this distribution for various numbers of samples, and test results as shown in the notebook. Then choose the number of samples to gather.




