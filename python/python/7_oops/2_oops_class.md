|  No.  | [Class]()                                                                                        |
| :---: | ------------------------------------------------------------------------------------------------ |
|       | [What is Class?](#ques--what-is-class)                                                           |
|       | [Accessing the attributes value different ways?](#accessing-the-attributes-value-different-ways) |
|       | [Change the value of the attribute?](#change-the-value-of-the-attribute)                         |
|       | [What is __init_ _ Method?](#ques--what-is-init-method)                                        |

### Ques.  What is Class?
* Class is a template/blueprint/prototype for creating objects.
* class is a collection of attributes and method.
* The class is a collection of objects.
* It is a logical entity that has some specific attributes and methods.
* To define a class in Python, you can use the class keyword, followed by the class name and a colon. Inside the class, an __init__ method has to be defined with def. This is the initializer that you can later use to instantiate objects. It's similar to a constructor in Java. __init__ must always be present! It takes one argument: self, which refers to the object itself. Inside the method, the pass keyword is used as of now, because Python expects you to type something there.
* **Example:-** Email is a class and headding, particiant, attachment is object

#### Define a class
* We use the class keyword followed by the class name and a colon. The following example defines a Person class:
```python
class Person:
    pass
```
* If the class name contains multiple words, you use the CamelCase format, for example SalesEmployee.
* When printing out the person object, you’ll see its name and memory address:
```python
class Person:
    pass

print(person)

Output:- <__main__.Person object at 0x000001C46D1C47F0>
```
* To get an identity of an object, you use the id() function. For example:
```python
print(id(person)) # 1943155787760
```

### Python get Class Variables
* Get the values of **class variables**
```python
# using calss name
class Student:
    name = 'mohit saxena'
    roll_no = '12845678'
    
print(Student.name)     # mohit saxena
print(Student.roll_no)  # 12845678


# using **getattr()** function:- The getattr() function accepts an object and a variable name. It returns the value of the class variable.
name = getattr(Student, 'name')
rollno = getattr(Student, 'roll_no')

print(name)     # mohit saxena
print(rollno)   # 12845678
```
* If you access a class variable that doesn’t exist, you’ll get an AttributeError exception.



### Set values for class variables
* To set a value for a class variable, you use the dot notation:

```python
# set the value using class
class Student:
    name = 'mohit saxena'
    roll_no = 12845678

Student.roll_no = 10     
print(Student.roll_no)    # output:- 10

# using setattr() built-in function
setattr(Student, 'roll_no', 10)
print(Student.roll_no)  # output:- 10
```


### Delete class variables
```python
class Student:
    name = 'mohit saxena'
    roll_no = '12845678'
    
print(Student.name)     # mohit saxena
print(Student.roll_no)  # 12845678

# using **delattr()** function:
delattr(Student, 'roll_no') # Output:- AttributeError: type object 'Student' has no attribute 'roll_no'

# using del keyword
del Student.roll_no
print(Student.roll_no)  # Output:- AttributeError: type object 'Student' has no attribute 'roll_no'
```

### Ques.  What is __init__ Method?
* **__init__** is a constructor method in Python and is automatically called to allocate memory when a new object/instance is created.
* All classes have a function called __init__() function, which is always excuted when the object is being initiated.
* Python always calls init function whatever you create them or not.

```python
class Student:
   def __init__(self, fname, lname):
       self.firstname = fname
       self.lastname = lname
       print("My name is " + self.firstname + " " + self.lastname)
# creating a new object
stu1 = Student("Mohit", "Saxena") #output:- My name is Mohit Saxena
```

* Since Python is a dynamic language, you can add a class variable to a class at runtime after you have created it. 
```python
class HtmlDocument:
    extension = 'html'
    version = '5'

HtmlDocument.media_type = 'text/html'
print(HtmlDocument.media_type)

Output:- text/html
```

* **Example 1**
```python
class Person:
  def __init__(self, name, age):
    self.f_name = name
    self.age = age

p1 = Person("John", 36)

print(p1.f_name) # John
print(p1.age)    #  36
```
* **Example 2**
```python
class Dog:

    def __init__(self, name, age):  
        self.name = name
        self.age = age

    def bark(self):
        print("bark bark!")

    def doginfo(self):
        print(self.name + " is " + str(self.age) + " year(s) old.")
        
ozzy = Dog("Ozzy", 2)
skippy = Dog("Skippy", 12)
filou = Dog("Filou", 8)

ozzy.bark()
skippy.doginfo()
filou.doginfo()

Output:-
bark bark!
Skippy is 12 year(s) old.
Filou is 8 year(s) old.
```

### Accessing the attributes value different ways?

* we have shown two ways of accessing the values of those attributes.
    1. One, by directly using the **class name** and the other by 
    2. using an **object(class instance)**. Assigning a class to a variable is known as object instantiation.
```python
class Scaler:
    Course1 = 'Python'
    Course2 = 'C++'
    Course3 = 'Java'
# Accessing the values of the attributes
print(Scaler.Course1)
print(Scaler.Course3)
# Accessing through object instantiation.
obj= Scaler()
print(obj.Course2)

Output:-
Python
Java
C++
```

### Change the value of the attribute?

* If we change the value of the attribute using the class name, then it would change across all the instances of that class. While if we change the value of an attribute using class instance(object instantiation), it would only change the value of the attribute in that instance only.
```python
class Scaler:
    Course = 'Python'
# Changing value using Class Name
Scaler.Course = 'Machine Learning'
obj= Scaler()
print(obj.Course)
# Changing value using Class Instance 
obj.Course = 'AI'
print(obj.Course)   # Value will change in this instance only
print('Using class instance would not reflect the changes to other instances')
print(Scaler.Course) # Value haven't changed
obj2= Scaler()
print(obj2.Course)   # Value haven't changed

Output:- 
Machine Learning
AI
Using class instance would not reflect the changes to other instances
Machine Learning
Machine Learning
```

