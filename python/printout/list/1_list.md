### **Ques. What is List?**
* Lists are used to store multiple items in a single variable.
* List items are **ordered**, **changeable**, and **allow duplicate** values.
* In Python lists are written with **square brackets[]**, separated by commas.
* The list is __changeable__, meaning that we can change, add, and remove items in a list after it has been created.
* list Allow Duplicates values. **Ex:-** list = ["apple", "banana", "cherry", "apple", "cherry"]
* List items can be of any data type. **Ex:-** list = ["abc", 34, True, 40, "male"]


```python
my_list = ["apple", "banana", "cherry", "banana"]   
my_list = [1, "Hello", 3.4]              
my_list = ["mouse", [8, 4, 6], ['a']]  # A list can also have another list as
                                       # an item. This is called a nested list. 
print(my_list)
```


### **Ques. List Length**
* use the len() function:
```python
thislist = ["apple", "banana", "cherry"]
print(len(thislist))

Output:- 3
```

### **Ques. How to Check if Item Exists?**
```python
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
  print("Yes, 'apple' is in the fruits list")

Output:- Yes, 'apple' is in the fruits list
```