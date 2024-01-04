### **Ques. What is python Variables?**
* Variables are containers for storing data values.
* A variable name must start with a letter or the underscore character.
* A variable name can only contain alpha-numeric characters and underscores
* A variable name cannot start with a number.
```python
x = 5
y = "John"
print(x)
print(y)

Output:- 
5
John
```

* **Case-Sensitive :** Variable names are case-sensitive (age, Age and AGE are three different variables)
```python
a = 4
A = "Sally"

print(a)
print(A)

Output:-
4
Sally
```

* **Variables Casting:** We want to specify the data type of a variable, this can be done with casting. and We can **get the data type** of a variable with the **type()** function.
```python
x = str(3)
y = int(3)
z = float(3)

print(x)
print(y)
print(z)

Output:- 
3
3
3.0
```
```python
x = 5
y = "John"
print(type(x))
print(type(y))

Output:-
<class 'int'>
<class 'str'>
```

* **Single or Double Quotes:-**  String variables can be declared either by using single or double quotes:
```python
x = "John"
print(x)
#double quotes are the same as single quotes:
x = 'John'
print(x)

Output:-
John
John
```

* **Assign Multiple Values:** Python allows you to assign values to multiple variables in one line.
```python
x, y, z = "Orange", "Banana", "Cherry"

print(x)
print(y)
print(z)

Output:- 
Orange
Banana
Cherry 
```

* **One Value to Multiple Variables:** And we can assign the same value to multiple variables in one line.
```python
x = y = z = "Orange"

print(x)
print(y)
print(z)

Output:-
Orange
Orange
Orange
```

* **Unpack a Collection:** If we have a collection of values in a list, tuple etc. Python allows you to extract the values into variables. This is called unpacking.
```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits

print(x)
print(y)
print(z)

Output:-

apple
banana
cherry
```