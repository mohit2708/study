### **Ques. Loop Lists?**
```python
# Loop Through a List
thislist = ["apple", "banana", "cherry"]
for x in thislist:
  print(x)

Output:- 
apple
banana
cherry
--------------------------------------------------------------------------------

# Loop Through the Index Numbers
# You can also loop through the list items by referring to their index number.
#Use the range() and len() functions to create a suitable iterable.
thislist = ["apple", "banana", "cherry"]
for i in range(len(thislist)):
  print(thislist[i])

Output:-
 apple
 banana
 cherry
```
* Using a **While Loop**
```python
thislist = ["apple", "banana", "cherry"]
i = 0
while i < len(thislist):
  print(thislist[i])
  i = i + 1

Output:-
apple
banana
cherry
```
* Looping Using **List Comprehension**
```python
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]

Output:-
apple
banana
cherry
```