|  No.  | [Class]()                                                                                     |
| :---: | --------------------------------------------------------------------------------------------- |
|       | [What is Object?](#ques-what-is-object)                                                       |
|       | [Delete the Object?](#ques-delete-the-object)                                                 |
|       | [Counting the Number of objects of a Class?](#ques-counting-the-number-of-objects-of-a-class) |

### Ques. What is Object?
* An object is a container that contains data and functionality.
* The object is an entity that has state and behavior. It may be any real-world object like the mouse, keyboard, chair, table, pen, etc.
* Before creating objects, you define a class first. And from the class, you can create one or more objects. The objects of a class are also called **instances** of a class.
* **For example:** if you have an employee class, then it should contain an attribute and method, i.e. an email id, name, age, salary, etc.

```python
class Person:
    pass

person = Person()
print(person)
```
```python
class car:
    a = "mohit"
    def __init__(self,modelname, year):  
        self.modelname = modelname  
        self.year = year
    def display(self):  
        print(self.modelname,self.year)  
  
c1 = car("Toyota", 2016)  
print(c1.a)       # Accessing Object's variables    Output:- mohit
c1.display()      # Accessing Object's functions    Output:- Toyota 2016
```

* Modifying Object's properties
```python
class Scaler:
  a = 10

# Declaring an object
obj1 = Scaler()
print(obj1.a)   # output:- 10

#Modifying value
obj1.a = 200
print("After modifying the object properties")  # output:- After modifying the object properties
print(obj1.a)   # output:- 200
```


* Here, the **self** is used as a reference variable, which refers to the current class object. It is always the first argument in the function definition. However, using self is optional in the function call.
* The **self-parameter** refers to the current instance of the class and accesses the class variables. We can use anything instead of self, but it must be the first parameter of any function which belongs to the class



### Ques. Delete the Object?
* We can **delete the properties of the object** or object itself by using the **del** keyword.
```python
# delete the properties of the object
class Student:
    def __init__(self,name):
        self.name = name

obj = Student("mohit")
print(obj.__dict__)   # Output:- {'name': 'mohit'}
del obj.name
print(obj.__dict__)   # Output:- {}


# Deleting the object itself by del keyword
obj = Student("mohit")
print(obj.__dict__)   # Output:- {'name': 'mohit'}
del obj
print(obj.__dict__)   # Output:- ERROR!
```


### Ques. Counting the Number of objects of a Class?
```python
class Employee:
    count = 0
    def __init__(self):
        Employee.count = Employee.count + 1


# creating objects
e1 = Employee()
e2 = Employee()
e2 = Employee()
print("The number of Employee:", Employee.count)

Output:- The number of employee: 3
```

### Ques. other example:
```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
    
    def get_avg(self):
        sum = 0
        lgh = len(self.marks) 
        for val in self.marks:
            sum = sum+val
            avg = sum/lgh
        print("my name is",self.name,"and my marks is", avg)
#  + self.name + " and my marks is " + avg          
# creating a new object
stu1 = Student("Mohit", [97,98,96])
stu1.get_avg()

stu1.name = "saxena"
stu1.get_avg()

Output:-
my name is Mohit and my marks is 97.0
my name is saxena and my marks is 97.0
```
### Ques. 

```python
class Account:
    def __init__(self, acc_no, bal):
        self.acc_no = acc_no
        self.bal = bal
    
    def debit(self, amount):
        self.bal -= amount
        print("debited amount is ", amount, "my bal is", self.finalAmount())
    
    def credit(self,amount):
        self.bal += amount
        print("credit amount is ", amount, "my bal is", self.finalAmount())
        
    def finalAmount(self):
        return self.bal
    
# creating a new object
stu1 = Account(564654,10000)
stu1.debit(900)
stu1.credit(800)

Output:-
debited amount is  900 my bal is 9100
credit amount is  800 my bal is 9900
```
