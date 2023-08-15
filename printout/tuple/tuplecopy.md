* Check if Item Exists 
```python
thistuple = ("apple", "banana", "cherry")
if "apple" in thistuple:
  print("Yes, 'apple' is in the fruits tuple")

Output:- Yes, 'apple' is in the fruits tuple
```

### **copy tuple**
* We can use the 'tuple( )' constructor to make a copy of the Tuple.
```python
x = ("Mohan", "Kriti", "Salim")
y = tuple(x)
print(y) 

Output:- ('Mohan', 'Kriti', 'Salim')
```
* With the help of **copy** and **deepcopy**
```python
a = (1, 2, [])
c = copy(a)
d = deepcopy(a)
print(c, d)

Output:- (1, 2, []) (1, 2, [])
```


### **Unpack Tuples**
* packing a Tuple:- When we create a tuple, we normally assign values to it. This is called "packing" a tuple.
```python
fruits = ("apple", "banana", "cherry")
print(fruits)

Output:- ('apple', 'banana', 'cherry')

#Example2
def fun(*abc):
    print(abc)
fun(2,5,6)

Output:- (2, 5, 6)

#Example3
def fun(**abc):
    print(abc)
fun(a=2,b=5,c=6)

Output:- {'a': 2, 'b': 5, 'c': 6}
```
* Unpacking a Tuple:- in Python, we are also allowed to extract the values back into variables. This is called "unpacking".
```python
fruits = ("apple", "banana", "cherry")
(green, yellow, red) = fruits

print(green)
print(yellow)
print(red)

Output:- 
apple
banana
cherry

# Example2 Using Asterisk (*):-
#If the number of variables is less than the number of values, you can add an * to the variable name and the values will be assigned to the variable as a list. 
fruits = ("apple", "mango", "papaya", "pineapple", "cherry")

(green, *tropic, red) = fruits

print(green)
print(tropic)
print(red)

Output:- 
apple
['mango', 'papaya', 'pineapple']
cherry

# Example3
def fun(a,b,c,d):
    print(a,b,c,d)
list = [2,5,7,4]
fun(*list)

Output:- 2 5 7 4


# Example4
x=[1,5]
print(list(range(*x)))

Output:- [1, 2, 3, 4]
```


### Join Tuples
* Using **plus(+)** operator
```python
# Join Two Tuples
tuple1 = ("a", "b" , "c")
tuple2 = (1, 2, 3)

tuple3 = tuple1 + tuple2
print(tuple3)

Output:- 
('a', 'b', 'c', 1, 2, 3)
```
* Using **Multiply(*)** operator
```python
fruits = ("apple", "banana", "cherry")
mytuple = fruits * 2

print(mytuple)
Output:- ('apple', 'banana', 'cherry', 'apple', 'banana', 'cherry')
```

### **Tuple Methods**
| Method  | Description                                                                             |
| ------- | --------------------------------------------------------------------------------------- |
| count() | Returns the number of times a specified value occurs in a tuple                         |
| index() | Searches the tuple for a specified value and returns the position of where it was found |

```python
# Tuple count() Method
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)
x = thistuple.count(5)
print(x)

Output:- 2
-------------------------------------------------------------------------------

# Tuple index() Method:- Search for the first occurrence of the value 8, and return its position.
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)
x = thistuple.index(8)
print(x)

Output:- 3
```


### **Ques. Difference between List and Tuples in Python?**
|                                                     List                                                     |                                            Tuples                                             |
| :----------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------: |
|                                   List is mutable. i.e they can be edited.                                   |                 Tuple is immutable. (tuples are lists which can’t be edited).                 |
|                               List iteration is slower and is time consuming.                                |                                  Tuple iteration is faster.                                   |
|                            List is useful for insertion and deletion operations.                             |               Tuple is useful for readonly operations like accessing elements.                |
|                                           List has a large memory.                                           |                                   Tuple has a small memory.                                   |
| List is stored in two blocks of memory (One is fixed sized and the other is variable sized for storing data) |                         Tuple is stored in a single block of memory.                          |
|                                     List provides many in-built methods.                                     |                              Tuples have less in-built methods.                               |
|                                     List operations are more error prone                                     |                                  Tuples operations are safe.                                  |
|      A list has data stored in  square brackets [] brackets. For example, list_1 = [10, ‘Chelsea’, 20]       | A tuple has data stored in parantheses () brackets. For example, tup_1 = (10, ‘Chelsea’ , 20) |



### **Ques. Convert a list into a tuple?**
```python
# Using tuple() builtin function
list = [1,2,3,4]
result = tuple(list)
print(type(result))

Output:- <class 'tuple'>
-------------------------------------------------------------

# Using loop inside the tuple
sample_list = ['Compile', 'With', 'Favtutor']
tuple1 = tuple(i for i in sample_list)
print(tuple1)

Output:- ('Compile', 'With', 'Favtutor')
-------------------------------------------------------------

# Unpack list inside the parenthesis
sample_list = ['Compile', 'With', 'Favtutor']

#unpack list items and form tuple
tuple1 = (*sample_list,)

print(tuple1)
print(type(tuple1))

Output:- 
('Compile', 'With', 'Favtutor')
<class 'tuple'>
```

### **Ques. How to Sort List Of Tuples By The First Element?**
```python
tup= [('C#',1), ('Go',7), ('Basic',8), ('Python',60)]
tup.sort()  
print(tup)

Output:- [('Basic', 8), ('C#', 1), ('Go', 7), ('Python', 60)]
```

### **Ques. How to Sort List Of Tuples By Second Element?**
```python
tup= [('C#',1), ('Go',7), ('Basic',8), ('Python',60)]
tup.sort(key = lambda x:x[1])
print(tup)

Output:- [('C#', 1), ('Go', 7), ('Basic', 8), ('Python', 60)]
```