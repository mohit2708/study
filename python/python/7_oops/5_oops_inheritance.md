### **Ques What is Inheritance?**
* The process of inheriting all the methods and properties of the parent class into a child class is called inheritance.
* **Benefits:-** It provides the reusability of a code. We don’t have to write the same code again and again.

```python
class house:   
    height = “572ft”                 # predefined attributes of a class
    architect = “John Doe”
  
    def display_height(self):
        print("This house is " + self.height)    # methods for displaying height
    def display_architect(self):
        print (“The architect is “ + self.architect)  # methods for displaying architect

# Driver Code
Bungalow = house()            # object creation
print(Bungalow.height)        # accessing class attributes      Output:- 572ft
Bungalow.display_height()     # calling method through object   Output:- This house is 572ft
Bungalow.display_architect()  # calling method through object   Output:- The architect is John Doe
```

#### Types Of Inheritance?
- [**Ques What is Inheritance?**](#ques-what-is-inheritance)
  - [Types Of Inheritance?](#types-of-inheritance)
    - [Single Inheritance:-](#single-inheritance-)
    - [Multiple Inheritance:-](#multiple-inheritance-)
    - [Multi-Level Inheritance:-](#multi-level-inheritance-)
    - [Hierarchical Inheritance:-](#hierarchical-inheritance-)
    - [Hybrid Inheritance:-](#hybrid-inheritance-)
- [Ques. What is the super() Function?](#ques-what-is-the-super-function)
  - [super() with Single Inheritance](#super-with-single-inheritance)
  - [super() with Multiple Inheritance](#super-with-multiple-inheritance)
##### Single Inheritance:-
* In single inheritance, a child class inherits from a single-parent class. Here is one child class and one parent class.
```python
    A
    |
    |
    |
    B
```
```python
# Base class
class Vehicle:
    def Vehicle_info(self):
        print('Inside Vehicle class')

# Child class
class Car(Vehicle):
    def car_info(self):
        print('Inside Car class')

# Create object of Car
car = Car()

# access Vehicle's info using car object
car.Vehicle_info()
car.car_info()

Output:- 
Inside Vehicle class
Inside Car class
```
##### Multiple Inheritance:-
* In multiple inheritance, a single child class is inherited from two or more parent classes. This means the child class has access to all the methods and attributes of all the parent classes.
```python
    A        B
    \       /
     \     /
      \   /
       \ /
        C
```
```python
class Person:
    def person_info(self, name, age):
        print('Inside Person class')
        print('Name:', name, 'Age:', age)

# Parent class 2
class Company:
    def company_info(self, company_name, location):
        print('Inside Company class')
        print('Name:', company_name, 'location:', location)

# Child class
class Employee(Person, Company):
    def Employee_info(self, salary, skill):
        print('Inside Employee class')
        print('Salary:', salary, 'Skill:', skill)

# Create object of Employee
emp = Employee()

# access data
emp.person_info('Jessa', 28)
emp.company_info('Google', 'Atlanta')
emp.Employee_info(12000, 'Machine Learning')

Output:-
Inside Person class
Name: Jessa Age: 28
Inside Company class
Name: Google location: Atlanta
Inside Employee class
Salary: 12000 Skill: Machine Learnings
```

##### Multi-Level Inheritance:-
* In multilevel inheritance, a class inherits from a child class or derived class. Suppose three classes A, B, C. A is the superclass, B is the child class of A, C is the child class of B. In other words, we can say a chain of classes is called multilevel inheritance.
```python
    A
    |
    |
    B
    |
    |
    C
```
```python
# Base class
class Vehicle:
    def Vehicle_info(self):
        print('Inside Vehicle class')

# Child class
class Car(Vehicle):
    def car_info(self):
        print('Inside Car class')

# Child class
class SportsCar(Car):
    def sports_car_info(self):
        print('Inside SportsCar class')

# Create object of SportsCar
s_car = SportsCar()

# access Vehicle's and Car info using SportsCar object
s_car.Vehicle_info()
s_car.car_info()
s_car.sports_car_info()

Output:-
Inside Vehicle class
Inside Car class
Inside SportsCar class
```

##### Hierarchical Inheritance:-
* In Hierarchical inheritance, more than one child class is derived from a single parent class. In other words, we can say one parent class and multiple child classes.
```python
                ParentClass
                  / | \
                 /  |  \
                /   |   \
              CC1  CC2  CC3
```
```python
class Vehicle:
    def info(self):
        print("This is Vehicle")

class Car(Vehicle):
    def car_info(self, name):
        print("Car name is:", name)

class Truck(Vehicle):
    def truck_info(self, name):
        print("Truck name is:", name)

obj1 = Car()
obj1.info()
obj1.car_info('BMW')

obj2 = Truck()
obj2.info()
obj2.truck_info('Ford')

Output:-
This is Vehicle
Car name is: BMW
This is Vehicle
Truck name is: Ford
```

##### Hybrid Inheritance:-
* Hybrid Inheritance is the mixture of two or more different types of inheritance. Here we can have many to many relations between parent classes and child classes with multiple levels.
```python
         PC
        /|\
       / | \
    CC1  |  CC2
     \   |  /
      \  | /
        CC3
```
```python
class Vehicle:
    def vehicle_info(self):
        print("Inside Vehicle class")

class Car(Vehicle):
    def car_info(self):
        print("Inside Car class")

class Truck(Vehicle):
    def truck_info(self):
        print("Inside Truck class")

# Sports Car can inherits properties of Vehicle and Car
class SportsCar(Car, Vehicle):
    def sports_car_info(self):
        print("Inside SportsCar class")

# create object
s_car = SportsCar()

s_car.vehicle_info()
s_car.car_info()
s_car.sports_car_info()

Output:-
Hello Parent1
Hello Child1

Hello Parent1
Hello Parent2
Hello Child1
Hello Child2
```

### Ques. What is the super() Function?
* Super() method is used to access method and properties of the parant class.
* The **super** function returns a temporary object of the parent class that allows us to call a parent class method inside a child class method.
* **Benefits** of using the super() function.
  * We are not required to remember or specify the parent class name to access its methods.
  * We can use the super() function in both single and multiple inheritances.
  * The super() function support code reusability as there is no need to write the entire function
```python
class Company:
    def company_name(self):
        return 'Google'

class Employee(Company):
    def info(self):
        # Calling the superclass method using super()function
        c_name = super().company_name()
        print("Jessa works at", c_name)

# Creating object of child class
emp = Employee()
emp.info()

Output:- Jessa works at Google
```


#### super() with Single Inheritance
```python
class Animal:
    def smell(self,name):
        print(name, "can smell")
        
class Dog(Animal):
    def __init__(self):
        super().smell("Dog")
        
    def bark(self):
        print("Dog can bark")
    
dog = Dog()     # Output:- Dog can smell
dog.bark()  # Output:- Dog can bark
```
```python
class Parent:
    def __init__(self, name):
        self.name = name

    def display(self):
        print(f"Parent name: {self.name}")

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name) # Call the constructor of the parent class
        self.age = age

    def display(self):
        super().display()       # Call the display method of the parent class using super keyword
        Parent.display(self)    # Call the display method of the parent class using class name
        print(f"Child age: {self.age}")

# Example usage
parent = Parent("John")
parent.display()    # output:- Parent name: John

child = Child("Alice", 10)
child.display() # output:- Parent name: Alice, Parent name: Alice, Child age: 10
```

#### super() with Multiple Inheritance
```python
class Parent:
    def __init__(self):
        print("This is the parent class")
        
class Parent1:
    def __init__(self):
        print("This is the parent1 class")
        
class Child(Parent1, Parent):
    def __init__(self):
        ##Calling constructor of the Parnet 1 class
       super().__init__()
    
ob = Child() # output:- This is the parent1 class


# if we have inherit class parent and parent1
class Child(Parent, Parent1):
    def __init__(self):
        ##Calling constructor of the Parnet 1 class
       super().__init__()
    
ob = Child() # output:- This is the parent class
```