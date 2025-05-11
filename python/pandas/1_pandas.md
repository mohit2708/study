|  No.  | [Python Interview Questions](./0.0_python_questions.md)     |
| :---: | ----------------------------------------------------------- |
|       | [what is pandas?](#what-is-pandas)                          |
|       | [Creating an Empty DataFrame](#creating-an-empty-dataframe) |


### Install Jupyter Notebook
* Install the classic Jupyter Notebook with:
```python
pip install notebook
```
* To run the notebook:
```python
jupyter notebook
```

### Install Numpy
```python
pip install numpy
```


### what is pandas?
* Pandas is a Python library for data manipulation and analysis.
* The name "Pandas" has a reference to both "Panel Data", and "Python Data Analysis" and was created by Wes McKinney in 2008.

### Install Pandas
```python
pip install pandas
```
* upgrade pandas
```python
pip install --upgrade pandas
```

### Checking Pandas Version
```python
import pandas as pd

print(pd.__version__)   # Output:- 2.2.2
```

### Pandas provides two types of classes for handling data:
1. **Series**: a one-dimensional labeled array holding data of any type such as integers, strings, Python objects etc.
2. **DataFrame**: a two-dimensional data structure that holds data like a two-dimension array or a table with rows and columns.

### Import Pandas
```python
import pandas

mydataset = {
  'cars': ["BMW", "Volvo", "Ford"],
  'passings': [3, 7, 2]
}

myvar = pandas.DataFrame(mydataset)

print(myvar)
Output:- 
    cars    passings
0   BMW         3
1   Volvo       7
2   Ford        2
```
* **alias:** In Python alias are an alternate name for referring to the same thing.
```python
import pandas as pd

mydataset = {
  'cars': ["BMW", "Volvo", "Ford"],
  'passings': [3, 7, 2]
}

myvar = pd.DataFrame(mydataset)

print(myvar)
```


### Creating an Empty DataFrame
```python
import pandas as pd
df = pd.DataFrame()
print(df)

Output:-
Empty DataFrame
Columns: []
Index: []
```

### Creating a DataFrame from a List
```python
import pandas as pd

lst = ['mohti', 'is', 'good', 'boy']

df = pd.DataFrame(lst)
print(df)

Output:-
        0
0   mohit
1     is
2   good
3    boy
```

### Creating DataFrame from dict of Numpy Array
```python
import numpy as np
import pandas as pd

data = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
df = pd.DataFrame(data, columns=['A', 'B', 'C'])
print(df)

Output:-
   A  B  C
0  1  2  3
1  4  5  6
2  7  8  9
```

### Creating a DataFrame from a List of Dictionaries
```python
import pandas as pd

dict = {'name':["aparna", "pankaj", "sudhir", "Geeku"],
        'degree': ["MBA", "BCA", "M.Tech", "MBA"],
        'score':[90, 40, 80, 98]}

df = pd.DataFrame(dict)

print(df)

Output:-
     name  degree  score
0  aparna     MBA     90
1  pankaj     BCA     40
2  sudhir  M.Tech     80
3   Geeku     MBA     98
```



### what is concat?
* The pandas. concat() function concatenates and combines multiple DataFrames or Series into a single, unified DataFrame or Series.

### Pandas

* Install pandas
```python
pip install pandas
```
