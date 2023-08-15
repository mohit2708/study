### **Ques. Remove Item of set?**
* **remove() method:-** If the item to remove does not exist, remove() will raise an error.
```python
thisset = {"apple", "banana", "cherry"}
thisset.remove("banana")
print(thisset)
			
Output:- {'apple', 'cherry'}
```

* **discard() method:-** If the item to remove does not exist, **discard()** will NOT raise an error.
```python
thisset = {"apple", "banana", "cherry"}
thisset.discard("banana")
print(thisset)
			
Output:- {'apple', 'cherry'}
```

* **pop() method:-** you can also use the **pop()** method to remove an item, but this method will remove the last item. Remember that sets are unordered, so you will not know what item that gets removed.
```python
thisset = {"apple", "banana", "cherry"}
x = thisset.pop()
print(x) #removed item
print(thisset) #the set after removal
			
Output:-
banana
{'cherry', 'apple'}
```

* The **clear()** method empties the set.
```python
thisset = {"apple", "banana", "cherry"}
thisset.clear()
print(thisset)
			
output:- set()
```

* The **del** keyword will delete the set completely.
```python
--------------------------------------------------------------------
# The del keyword will delete the set completely:
thisset = {"apple", "banana", "cherry"}
del thisset
print(thisset) #this will raise an error because the set no longer exists
			
output:- Error
```

### **Ques. What is difference between Discard() and Remove()?**
* This method is different from the discard() method, because the remove() method will raise an error if the specified item does not exist, and the discard() method will not.