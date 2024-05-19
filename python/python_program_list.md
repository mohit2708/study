### Table of Contents

|  No.  | Questions                                                                                            |
| :---: | ---------------------------------------------------------------------------------------------------- |
|   1   | [Hello World](#ques-print-hello-world)                                                               |
|       | [convert a list to string](#program-to-convert-a-list-to-string)                                     |
|       | [Interchange first and last elements in a list](#ques-interchange-first-and-last-elements-in-a-list) |


## List Questions
### Ques. Find the Length of a List?
* using function
```python
li = [10, 20, 30]
n = len(li)
print("The length of list is: ", n)

Output: -  3
```
* Find the Length of a List Using Naive Method
```python
test_list = [1, 4, 5, 7, 8]
counter = 0
for i in test_list:
    counter = counter + 1
print("Length of list using naive method is : " + str(counter))
```

### Ques. Interchange first and last elements in a list?
* Using function
```python
def interchangeFirstAndLastElements(list):
    list[0], list[-1] = list[-1], list[0]
    return list

list = [12, 35, 9, 56, 24]
modified_list = interchangeFirstAndLastElements(list)
print(modified_list)
```
* without temp variable
```python
list = [12, 35, 9, 56, 24]
list[0] = list[-1]
list[-1] = list[0]
print(list)
```
* With temp variable
```python
list = [12, 35, 9, 56, 24]
length_of_list = len(list)
temp = list[0]
list[0] = list[length_of_list - 1]
list[length_of_list - 1] = temp
print(list)

Output:- [24, 35, 9, 56, 12]
```

### Ques. Find even numbers from the list?
```python
list1 = [10, 21, 4, 45, 66, 93]
for num in list1:
    if num % 2 == 0:
        print(num, end=" ")
```


### Ques. find the single number of the list?
```python
mylist = [1,2,2,3,3,4,5,5,5,6,6,6,6]
new_list = []
for num in mylist:
    if(mylist.count(num) == 1):
        new_list.append(num)

print(new_list)

Output:-[1, 4]
```