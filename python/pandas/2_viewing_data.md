
### Pandas Dataframe/Series.head() method
* Pandas head() method is used to return top n (**5 by default**) rows of a data frame or series. but you can specify a different number as an argument.
```python
import pandas as pd

# Sample DataFrame
data = {'col_1': [1, 2, 3, 4, 5, 6], 
        'col_2': ['A', 'B', 'C', 'D', 'E', 'F']}
df = pd.DataFrame(data)

# Get the first 3 rows
print(df.head(3))
# Expected Output:
#    col_1 col_2
# 0      1     A
# 1      2     B
# 2      3     C

# Get the first 5 rows (default)
print(df.head())
# Expected Output:
#    col_1 col_2
# 0      1     A
# 1      2     B
# 2      3     C
# 3      4     D
# 4      5     E
```


### Dataframe/Series.tail() method
* The tail() method in Pandas is used to retrieve the last n rows of a DataFrame or Series. By default, it returns the last **5 rows** if no argument is specified.
```python
import pandas as pd

# Creating a DataFrame
data = {'col_1': [3, 2, 1, 0, 4], 'col_2': ['a', 'b', 'c', 'd', 'e']}
df = pd.DataFrame(data)

# Retrieving the last 2 rows
last_two_rows = df.tail(2)
print(last_two_rows)
# Expected Output
#    col_1 col_2
# 3      0     d
# 4      4     e

# Retrieving the last 5 rows
last_five_rows = df.tail()
print(last_five_rows)
# Expected Output
#    col_1 col_2
# 0      3     a
# 1      2     b
# 2      1     c
# 3      0     d
# 4      4     e
```

### DataFrame describe() Method
* describe() method in Pandas is used to generate descriptive statistics of DataFrame columns. It gives a quick summary of key statistical metrics like **mean**, **standard deviation**, **percentiles**, and more. By default, describe() works with numeric data but can also handle categorical data, offering tailored insights based on data type.
#### Parameters:
* **percentiles**: A list of numbers between 0 and 1, specifying which percentiles to return. The default is None, which returns the 25th, 50th, and 75th percentiles.
* **include**: A list of data types to include in the summary. You can specify data types such as int, float, object (for strings), etc. The default is None, meaning all numeric types are included.
* **exclude**: A list of data types to exclude from the summary. This parameter is also None by default, meaning no types are excluded.
```python
count: Total number of non-null values in the column.
mean: Average value of the column.
std: Standard deviation, showing how spread out the values are.
min: Minimum value in the column.
25%: 25th percentile (Q1).
50%: Median value (50th percentile).
75%: 75th percentile (Q3).
max: Maximum value in the column.
```
```python
import pandas as pd
data = [[10, 18, 11], [13, 15, 8], [9, 20, 3]]
df = pd.DataFrame(data)
print(df.describe())

Output:-
                0          1          2
count   3.000000   3.000000   3.000000
mean   10.666667  17.666667   7.333333
std     2.081666   2.516611   4.041452
min     9.000000  15.000000   3.000000
25%     9.500000  16.500000   5.500000
50%    10.000000  18.000000   8.000000
75%    11.500000  19.000000   9.500000
max    13.000000  20.000000  11.000000
```