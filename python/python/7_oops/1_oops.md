|  No.  | [Python Oops Interview Questions](./7_oops/1_oops.md)                                          |
| :---: | ---------------------------------------------------------------------------------------------- |
|       | [Object-Oriented Programming (OOPS)?](#object-oriented-programming-oops)                       |
|       | [What is the use of self in Python?](#ques-what-is-the-use-of-self-in-python)                  |
|       | [What is pass in Python?](#ques-what-is-pass-in-python)                                        |
|       | [What is break, continue and pass in Python?](#ques-what-is-break-continue-and-pass-in-python) |
|       | [What is issubclass()?](#ques-what-is-issubclass)                                              |
|       | [What is __str_ _ and __repr_ _?](#ques-what-is-str-and-repr)                                  |
|       | [What is Abstract Method?](#ques-what-is-abstract-method)                                      |
|       | [What is Concrete Method?](#ques-what-is-concrete-method)                                      |
|       | [Difference between method and function?](#difference-between-method-and-function)             |

### Object-Oriented Programming (OOPS)
* Object-oriented programming (OOP) is a programming style that organizes code around objects, rather than functions and logic.
* Main Concepts of Object-Oriented Programming (OOPs) 
* [Class](#ques-What-is-Class)
* [Objects](#ques-What-is-Object)
* Polymorphism
* Encapsulation
* Inheritance
* Data Abstraction
  

### Ques. What is the use of self in Python?
* The Self parameter is a reference to the current instance of the class, we can access the attributes and methods of the class in python.
```python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("Mohit", 36)
p1.myfunc()     # Output:- Hello my name is Mohit
```
* We can give any name in place of self but first parameter is compulsory.
```python
class Person:
  def __init__(mysillyobject, name, age):
    mysillyobject.name = name
    mysillyobject.age = age

  def myfunc(abc):
    print("Hello my name is " + abc.name)

p1 = Person("John", 36)
p1.myfunc()
```


### Ques. What is pass in Python?
* The pass keyword represents a null operation in Python.
* Without the pass statement in the following code, we may run into some errors during code execution.
```python
def myEmptyFunc():
   # do nothing
   pass
myEmptyFunc()    # nothing happens
## Without the pass keyword
# File "<stdin>", line 3
# IndentationError: expected an indented block
```

### Ques. What is break, continue and pass in Python?
* **Break:-** The break statement terminates the loop immediately and the control flows to the statement after the body of the loop.
* **Continue:-** The continue statement terminates the current iteration of the statement, skips the rest of the code in the current iteration and the control flows to the next iteration of the loop.
* **Pass:-** As explained above, the pass keyword in Python is generally used to fill up empty blocks and is similar to an empty statement represented by a semi-colon in languages such as Java, C++, Javascript, etc.
```python
pat = [1, 3, 2, 1, 2, 3, 1, 0, 1, 3]
for p in pat:
   pass
   if (p == 0):
       current = p
       break
   elif (p % 2 == 0):
       continue
   print(p)    # output => 1 3 1 3 1
print(current)    # output => 0
```


### Ques. What is issubclass()?
* we can use Python built-in function issubclass(). This function returns True if the given class is the subclass of the specified class. Otherwise, it returns False.
```python
Syntex:- issubclass(class, classinfo)
```


### Ques. What is __str__ and __repr__?
* The __str__ method also known as a "dunder" method (double underscore method), that defines the string representation of an object. It's used to return a **human-readable** string when the built-in functions str() or print() are called on an instance of a class.
```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author
    def __str__(self):
        return f'"{self.title}" by {self.author}'

book = Book("C++", "E balaguswami")
print(book) # Output: "C++" by E balaguswami
print(str(book))   # Output: '"C++" by E balaguswami'


# Without a __str__ method, Python uses the default representation, like 
# <__main__.Person object at 0x000001>.
```

* The repr() method returns a string containing a printable representation of an object. The repr() function calls the underlying __repr__() function of the object.
* **__repr__** method returns a string representation of an object that is **machine-readable**.
```python
import datetime
today = datetime.datetime.now()
print(str(today))   # 2025-05-11 10:47:08.923663 (Readable end user format)
print(repr(today))  # datetime.datetime(2025, 5, 11, 10, 47, 8, 923663) (official developmrnt format)
```




### Ques. What is Abstract Method?
* To define an abstract **method** we use the **@abstractmethod** decorator of the abc module.
```python
from abc import ABC, abstractmethod
class DemoAbstractClass(ABC):
	@abstractmethod
	def abstract_method_name(self):
    	Pass
```

### Ques. What is Concrete Method?
* A concreate method is a method whose action is defined in the abstract class itself.
```python
from abc import ABC, abstractmethod
class Father(ABC):
    @abstractmethod
    def disp(self): 
        pass                                # method without body
    def show(self):
        print("concrete method")            # concrete Method / method with body
```

```python
class Father:
    def __init__(self, fname, lname):
        self.first_name = fname
        self.last_name = lname
    
    def show_data(self):
        print(self.first_name)

obj = Father('mohit','saxena')
obj.show_data()
```

### Difference between method and function?
#### Function
* A function is a block of code that performs a specific task and can be called independently from anywhere in your program.
* It is defined using the def keyword.
* It can take arguments (input values) and return values (output values).
```python
def add_numbers(x, y):
    return x + y

result = add_numbers(5, 3)
print(result)
```
#### Method
* A method is a function that is associated with an object or a class.
* It is defined within a class and operates on the data or attributes of that class.
* It is called using the dot notation on an object of the class.
```python
class Dog:
    def bark(self):
        print("Woof!")

my_dog = Dog()
my_dog.bark()
```

### What is Python Enumeration?
* In Python, an enumeration (or "enum") is a class that defines a set of symbolic names (constants) that are bound to unique, constant values. Enums are created using the enum module and are typically used to represent groups of related constants, making code more readable and maintainable.
```python
from enum import Enum

class TrafficLight(Enum):
    RED = 1
    YELLOW = 2
    GREEN = 3

# Accessing enum members by name:
print(TrafficLight.RED.name)  # Output: RED
print(TrafficLight.GREEN.value) # Output: 3

# Accessing enum members by value:
print(TrafficLight(1).name) # Output: RED
print(TrafficLight(3).value) # Output: 3
```