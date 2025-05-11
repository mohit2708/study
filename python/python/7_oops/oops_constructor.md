### **Ques. What is a constructor in Python?**
* In Python, the __init__() method is a special constructor method that is automatically called when an object is created, and it is called once for each instance of the class.
* If two objects are created from the same class, the constructor will be called separately for each object.
* If you don't define an __init__() method in your class, Python automatically provides a default constructor that takes no arguments.

* Example:-
```python
class Student:
    # constructor
    # initialize instance variable
    def __init__(self, name):
        print('Inside Constructor')
        self.name = name
        print('All variables initialized')

    # instance Method
    def show(self):
        print('Hello, my name is', self.name)


# create object using constructor
s1 = Student('Emma')
s1.show()

Output:-
Inside Constructor
All variables initialized
Hello, my name is Emma
```

d. Why used constructor?
e. Advantage of constructor


* **Types of Constructors:-**
  * Default Constructor
  * Non-parametrized constructor
  * Parameterized constructor

#### Default Constructor:- 
* The default constructor is not present in the source py file. 
```python
class Employee:

    def display(self):
        print('Inside Display')

emp = Employee()
emp.display()

Output:-Inside Display
```

#### Non-parametrized constructor
* A constructor without any arguments is called a non-parameterized constructor. This type of constructor is used to initialize each object with default values.
```python
class Company:

    # no-argument constructor
    def __init__(self):
        self.name = "Mohit"
        self.address = "Greater Noida"

    # a method for printing data members
    def show(self):
        print('Name:', self.name, 'Address:', self.address)

# creating object of the class
cmp = Company()

# calling the instance method using the object
cmp.show()  # Output:- Name: Mohit Address: Greater Noida
```

#### Parameterized Constructor:-
* A constructor with defined parameters or arguments is called a parameterized constructor. We can pass different values to each object at the time of creation using a parameterized constructor.
* The first parameter to constructor is self that is a reference to the being constructed, and the rest of the arguments are provided by the programmer. 
```python
class Employee:
    # parameterized constructor
    def __init__(self, name, age, salary):
        self.name = name
        self.age = age
        self.salary = salary

    # display object
    def show(self):
        print(self.name, self.age, self.salary)

# creating object of the Employee class
emma = Employee('Emma', 23, 7500)
emma.show() # Output:- Emma 23 7500

kelly = Employee('Kelly', 25, 8500)
kelly.show() # Output:- Kelly 25 8500
```

### Ques. Constructor With Default Values?
* Python allows us to define a constructor with default values. The default value will be used if we do not pass arguments to the constructor at the time of object creation.
```python
class Student:
    # constructor with default values age and classroom
    def __init__(self, name, age=12, classroom=7):
        self.name = name
        self.age = age
        self.classroom = classroom

    # display Student
    def show(self):
        print(self.name, self.age, self.classroom)

# creating object of the Student class
emma = Student('Emma')
emma.show()

kelly = Student('Kelly', 13)
kelly.show()

Output:-
Emma 12 7
Kelly 13 7
```

### Ques. Constructor Overloading?
* Python does not support constructor overloading.
* If we define multiple constructors then, the interpreter will considers only the last constructor and throws an error if the sequence of the arguments doesn’t match as per the last constructor. 
```python
class Student:
    # one argument constructor
    def __init__(self, name):
        print("One arguments constructor")
        self.name = name

    # two argument constructor
    def __init__(self, name, age):
        print("Two arguments constructor")
        self.name = name
        self.age = age

# creating first object
emma = Student('Emma')  # output:- Student.__init__() missing 1 required positional argument: 'age'

# creating Second object
kelly = Student('Kelly', 13) # output:- Two arguments constructor
```