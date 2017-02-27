# Lab 1 steps


```bash
mkdir lab1
cd lab1
conda create -n EJE1
source activate EJE1
conda install jupyter
pip install scipy numpy pandas sklearn
jupyter notebook
```

New > Notebooks > Python 3

```python
from sklearn.datasets import load_iris
import numpy as np
import pandas as pd


irisdata = load_iris()

irisdata.target[[10, 25, 50]] # array([0, 0, 1])
list(irisdata.target_names) # ['setosa', 'versicolor', 'virginica']

data1 = pd.DataFrame(data= np.c_[irisdata['data'], irisdata['target']], columns= irisdata['feature_names'] + ['target'])

data1 # table with lots of things

print ("Num Features: " + str(len(irisdata['feature_names'])))
print ("Nombre de las features: " + ", ".join(irisdata['feature_names']) )
print ("Rango de valores del target: (" + str(min(irisdata['target'])) + ", " + str(max(irisdata['target'])) + ")")
print ("Valor medio de las features: " + str(list(np.mean(irisdata['data'], axis=0))) )



```

