# Can you apply machine learning on small data ?
## We hear a lot about big data, but what about small data ? :)\
Sometimes you just don't have the resources or necessary time to gather much data.

Accross the 7 projects of my training, I've been working on several hundred thousands, or millions of data instances on various topics.\
That's not exactly big data, but that's something you can apply machine learning to : KNN, linear regression, random forest, ...

But what if you have 150 instances only and 35 variables ? Will machine learning or statistical analysis help you solve your problem ?\
I guess it depends on various things:\
- The nature of variable distributions and the existence of "rare" values that you may miss in your sampling
- The complexity of relation between dependant variables (= features, in machine learning) and independant variables (= labels to predict)
- The amount of effect size
- The number of variables having an effect : 150 instances and 5 variables is completely different from 150 instances and 35 variables

## Practical test
### First, generate random data
So let's do a small practical test to get a feeling of what you could do with small number of instances :\

I've generated a random dataset of 162 instances x 35 variables.\
Though not totally random: I've let 5 of the 35 variables be calculated using some pre-determined coeficients of 20, 15, 10, 5, 2 multiplied by the random matrix.\

So, we know that only the first 5 variables have a predictable effect on the label
The 30 other variables are totally random.

Now how many data instances do we need to train a model that can detect variable importances ?









Then we try to run machine learning and correlation analysis of the result, to see if we can find which variables have an effect.

```python
import matplotlib.pyplot as plt
import numpy as np

import pandas as pd
import pandas_profiling

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import make_scorer
def precision_score_micro(y_true, y_pred):
    return(precision_score(y_true, y_pred, average='micro'))

from sklearn.metrics import precision_score
from sklearn.metrics import recall_score
from sklearn.metrics import accuracy_score
from sklearn.metrics import f1_score

from sklearn.model_selection import GridSearchCV
import seaborn as sns


# In[16]:


NB_SAMPLES = 2000  # Avec 2000 :  perf 80%, et on détecte les 5 coefs importants.  Avec 161 : perf 57% et on ne détecte que les 3 premiers coefs
NB_VARIABLES = 35


# In[17]:


coefs = np.zeros([NB_VARIABLES])
coefs[5:] = 0.2
coefs[0] = 20
coefs[1] = 15
coefs[2] = 10
coefs[3] = 5
coefs[4] = 2


# In[18]:


coefs


# In[19]:


X = np.random.randint(0,10,(NB_SAMPLES, NB_VARIABLES))


# In[20]:


X


# In[21]:


Y = (coefs.dot(X.T))


# In[22]:


Y


# In[23]:


Y = pd.cut(pd.DataFrame(Y)[0], bins=5, labels=['F1','F2','F3','F4','F5']).to_numpy()


# In[24]:


X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=0.2, random_state=42, shuffle = True)


# In[25]:


model = RandomForestClassifier(max_depth=10, max_features=20, max_leaf_nodes=50,
                       n_estimators=5000, random_state=42) 

model.fit(X_train, Y_train)


# In[26]:


Y_predict_train = model.predict(X_train)
Y_predict_test = model.predict(X_test)


# In[27]:


precision_score(Y_predict_train, Y_train, average='micro')


# In[28]:


precision_score(Y_predict_test, Y_test, average='micro')


# In[29]:


recall_score(Y_predict_test, Y_test, average='micro')


# In[30]:


model.classes_


# In[31]:


model.feature_importances_


# In[32]:


pd.DataFrame(model.feature_importances_).plot.bar()


# In[33]:


pd.DataFrame(Y)[0].value_counts().plot.bar()


# In[46]:


df = pd.concat([pd.DataFrame(X),pd.DataFrame(Y).rename(columns={0: 'Y'})], axis=1)


# In[47]:


pandas_profiling.ProfileReport(df)

```


