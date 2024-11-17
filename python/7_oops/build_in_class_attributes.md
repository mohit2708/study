### Built-In Class Attributes?
* The built-in class attributes provide us with information about the class.
* Using the dot (.) operator, we may access the built-in class attributes.
* The built-in class attributes in python are listed below −
1. __dict__ :- 
   * The **__dict__** attribute is a dictionary containing the namespace of a class or instance.
   * It holds the attributes and methods defined for the class or object, allowing dynamic inspection and manipulation of its members.
   * Example:-
```python
class Person:
   'My name is mohit saxena'

   def __init__(self):
      print("The __init__ method")

print(Person.__dict__)

Output:-
{'__module__': '__main__', '__init__': <function Person.__init__ at 0x7c736ba3c7c0>, '__dict__': <attribute '__dict__' of 'Person' objects>, '__weakref__': <attribute '__weakref__' of 'Person' objects>, '__doc__': None}
```
2. __doc__
   * The __doc__ attribute contains the string of the class documents.
```python
class Person:
   'My name is mohit saxena'

   def __init__(self):
      print("The __init__ method")

print(Person.__doc__)

Output:-
My name is mohit saxena
```
3. __name__
   * The __name__ attribute provides the name of the class to which it belongs.
   * It is used to retrieve the name of a class within the class definition or in instances of the class.
```python
class Person:
   'My name is mohit saxena'

   def __init__(self):
      print("The __init__ method")

print(Person.__name__)

Output:-
Person
```
4. __module__
   * The __module__ attribute in Python represents the name of the module in which a class is defined.
   * It allows you to access and retrieve the module name to which a particular class belongs.__module__ ` contains the name of that module. 
   * This attribute is especially useful when working with courses defined in modules.
```python
class Person:
   'My name is mohit saxena'

   def __init__(self):
      print("The __init__ method")

print(Person.__module__)

Output:-
__main__
```
5. __bases__
    * The __bases__ attribute in Python is used to access a tuple containing the base classes of a class.
    * It provides information about the direct parent classes from which the class inherits.
```python
class Person:
   'My name is mohit saxena'

   def __init__(self):
      print("The __init__ method")

print(Person.__bases__)

Output:-
(<class 'object'>,)
```
