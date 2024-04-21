### **Ques. Add List Items?**
* **Append method:-** add an item to the **end of the list**, use the **append()** method.
```python
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print(thislist)

Output:- ['apple', 'banana', 'cherry', 'orange']
```
* **Insert method:-** The **insert()** method inserts an item at the ***specified index***.
```python
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist)

Output:- ['apple', 'orange', 'banana', 'cherry']
```

* **Extend method:-** The **extend()** method does not have to append lists, you can **add any iterable** object (list, tuples, sets, dictionaries etc.).
```python
thislist = ["apple", "banana", "cherry"]
tropical = ("mango", "pineapple", "papaya")

thislist.extend(tropical)
print(thislist)

Output:- ['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
```