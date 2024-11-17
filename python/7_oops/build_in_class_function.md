### Built-In Class Functions In Python?
### Using getattr, setattr, delattr, hasattr in Python
1. getattr() Function
2. setattr() function
3. delattr() function
4. hasattr() function
   
#### getattr()
* **The getattr()** function returns the value of the specified attribute from the specified object.
* **syntex:-**  getattr(object, attribute)
```python
class Person:
  name = "John"
  age = 36
  country = "Norway"

x = getattr(Person, 'page', 'my message')

print(x)    # 36
```
```python
class Library:
    def __init__(self, id, name):
        self.bookId = id
        self.bookName = name
                
book = Library(101,"The Witchers")
book.getBookName()                  # The name of book is The Witchers
print(getattr(book,'bookName'))     # The Witchers
print(book.__dict__)
```

*  when the attribute does not exist then use the "default" parameter to write a message.
*  Syntex:- getattr(object, attribute)
```python
class Person:
  name = "John"
  age = 36
  country = "Norway"

x = getattr(Person, 'coun', 'default country')

print(x)
```
```python
class Library:
    def __init__(self, id, name):
        self.bookId = id
        self.bookName = name
                
book = Library(101,"The Witchers")            
print(getattr(book,'bookName'))
print(book.__dict__)
setattr(book,'bookName','python book')
print(getattr(book,'bookName'))
print(book.__dict__)
```

#### setattr()
* **setattr()** function sets the value of the specified attribute of the specified object.
* **syntex:-** setattr(object, attribute, value)
```python
class Person:
  name = "John"
  age = 36
  country = "Norway"

setattr(Person, 'age', 40)
# The age property will now have the value: 40
x = getattr(Person, 'age')

print(x)        # 40
```

#### delattr()
* The **delattr()** function will delete the specified attribute from the specified object.
* **syntex:-** delattr(object, attribute)
```python
class Person:
  name = "John"
  age = 36
  country = "Norway"

delattr(Person, 'name')
```
```python
class Library:
    def __init__(self, id, name):
        self.bookId = id
        self.bookName = name
                
book = Library(101,"The Witchers")            
print(delattr(book,'bookName'))
print(book.__dict__)    # {'bookId': 101} 
```

#### hasattr()
* The **hasattr()** function returns True if the specified object has the specified attribute, otherwise False.
```python
class Person:
  name = "John"
  age = 36
  country = "Norway"

x = hasattr(Person, 'age')

print(x)    # True
```

