### **Change or Update Tuples**
* Once a tuple is created, you cannot change its values. Tuples are unchangeable, or immutable as it also is called.
* You can convert the tuple into a list, change the list, and convert the list back into a tuple.
```python
x = ("apple", "banana", "cherry")
y = list(x)
y[1] = "kiwi"
x = tuple(y)

print(x)

Output:- ("apple", "kiwi", "cherry")
```
* **Change a Range of Item Values:-** 1 se 2 wale range ke element hut jaynge
```python
thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "mango")
y = list(thistuple)
y[1:3] = ["blackcurrant", "watermelon"]
thistuple = tuple(y)

print(thistuple)

Output:- ('apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango'))
```