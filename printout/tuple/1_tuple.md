### **Ques. What is Tuples?**
* Tuples are used to store multiple items in a single variable.
* A tuple is a collection which is **ordered** and **unchangeable** and **allow duplicate** values.
* Tuples are written with **round()** brackets.
* A tuple can contain different data types.
  
```python
thistuple = ("apple", "banana","abc", 34, True, 40, "male")
print(thistuple)
```

### **Tuple Length**
* To determine how many items a tuple has, use the **len()** function
```python
thistuple = tuple(("apple", "banana", "cherry"))
print(len(thistuple))

Output:- 3
```

### **Ques. Create Tuple With One Item?**
* We have to add a comma after the item, otherwise Python will not recognize it as a tuple.
```python
thistuple = ("apple",)
print(type(thistuple))

#NOT a tuple
thistuple = ("apple")
print(type(thistuple))

Output:-
<class 'tuple'>
<class 'str'>
```


### **tuple() Constructor?**
```python
thistuple = tuple(("apple", "banana", "cherry"))
print(thistuple)

Output:- ('apple', 'banana', 'cherry')
```