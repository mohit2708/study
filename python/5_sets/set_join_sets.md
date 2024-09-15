### **Ques. Join Two Set?**

* **NOTE:-** Note: Both union() and update() will exclude any duplicate items.

* The **union()** method returns a new set with all items from both sets.
```python
set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}
set3 = set1.union(set2)
print(set3)
			
output:- {'a', 1, 2, 3, 'b', 'c'}
```

* The **update()** method inserts the items in set2 into set1.
```python
set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}
set1.update(set2)
print(set1)
			
output:- {'b', 'c', 1, 'a', 2, 3}
```

* The **intersection_update()** method will keep only the items that are present in both sets.
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
x.intersection_update(y)
print(x)
			
output:- {'apple'}
```

* The **intersection()** method will return a new set, that only contains the items that are present in both sets.
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
z = x.intersection(y)
print(z)

output:- {'apple'}
```

* The **symmetric_difference_update()** method will keep only the elements that are NOT present in both sets.
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
x.symmetric_difference_update(y)
print(x)

output:- {'google', 'banana', 'microsoft', 'cherry'}
```

* The **symmetric_difference()** method will return a new set, that contains only the elements that are NOT present in both sets.
```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}
z = x.symmetric_difference(y)
print(z)
			
output:- {'google', 'banana', 'microsoft', 'cherry'}
```
