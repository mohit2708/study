### **Ques. Access List Items?**
```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[1])          #Output:- banana
print(thislist[-1])         #Output:- mango
print(thislist[:])          #Output:- ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:5])        #Output:- ['cherry', 'orange', 'kiwi']
print(thislist[:4])         #Output:- ['apple', 'banana', 'cherry', 'orange']
print(thislist[2:])         #Output:- ['cherry', 'orange', 'kiwi', 'melon', 'mango']
print(thislist[-4:-1])      #Output:- ['orange', 'kiwi', 'melon']
print(thislist[:-1])        #Output:- ['apple', 'banana', 'cherry', 'orange', 'kiwi', 'melon']
```

* Get the Items at Specified Intervals

```python
list = [9,3,6,4,7,3,1,4]
print(list[::2])    # Output:- [9, 6, 7, 1]
print(list[::-2])   # Output:- [4, 3, 4, 3]
print(list[::-1])   # Output:- [4, 1, 3, 7, 4, 6, 3, 9]  #reverse the List using slice
```

* Accessing elements from a multi-dimensional list
```python
List = [['my', 'name'], ['is'],['mohit','saxena']]
print(List[0][1])
print(List[1][0])

Output:-
name
is
```