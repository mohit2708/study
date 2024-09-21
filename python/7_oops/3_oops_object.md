|  No.  | [Class]()                                                                                     |
| :---: | --------------------------------------------------------------------------------------------- |
|       | [What is Object?](#ques-what-is-object)                                                       |
|       | [Delete the Object?](#ques-delete-the-object)                                                 |
|       | [Counting the Number of objects of a Class?](#ques-counting-the-number-of-objects-of-a-class) |

### Ques. What is Object?
* The object is an entity that has state and behavior. It may be any real-world object like the mouse, keyboard, chair, table, pen, etc.
* **For example:** if you have an employee class, then it should contain an attribute and method, i.e. an email id, name, age, salary, etc.
  
```python
class car:
    a = "mohit"
    def __init__(self,modelname, year):  
        self.modelname = modelname  
        self.year = year  
    def display(self):  
        print(self.modelname,self.year)  
  
c1 = car("Toyota", 2016)  
print(c1.a)             # Accessing Object's variables
c1.display()            # Accessing Object's functions

output:- 
mohit
Toyota 2016
```

* Modifying Object's properties
```python
class Scaler:
  a = 10

# Declaring an object
obj1 = Scaler()
print(obj1.a)

#Modifying value
obj1.a = 200
print("After modifying the object properties")
print(obj1.a) 

Output:-
10
After modifying the object properties
200
```


* Here, the **self** is used as a reference variable, which refers to the current class object. It is always the first argument in the function definition. However, using self is optional in the function call.
* The **self-parameter** refers to the current instance of the class and accesses the class variables. We can use anything instead of self, but it must be the first parameter of any function which belongs to the class



### Ques. Delete the Object?
We can delete the properties of the object or object itself by using the del keyword. Consider the following example.
```python
class Employee:  
  id = 10  
  name = "John"  
  def display(self):  
    print("ID: %d \nName: %s" % (self.id, self.name))  
      # Creating a emp instance of Employee class  
      emp = Employee()  
  
      # Deleting the property of object  
      del emp.id  

      # Deleting the object itself  
      del emp  
      emp.display()
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