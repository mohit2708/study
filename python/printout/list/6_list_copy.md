### **Ques. Copy Lists?**
* You cannot copy a list simply by typing list2 = list1, because: list2 will only be a reference to list1, and changes made in list1 will automatically also be made in list2.
* So Two method of the copy below.
* **copy() method**
```python
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print(mylist)

Output:- ['apple', 'banana', 'cherry']
```

* **list() method**
```python
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print(mylist)

Output:- ['apple', 'banana', 'cherry']
```