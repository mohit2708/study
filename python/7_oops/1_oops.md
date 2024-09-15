### **Object-Oriented Programming (OOPS)**
Main Concepts of Object-Oriented Programming (OOPs) 
* [Class](#ques-What-is-Class)
* [Objects](#ques-What-is-Object)
* Polymorphism
* Encapsulation
* Inheritance
* Data Abstraction
  

### **Ques. What is the use of self in Python?**
* Self is used to represent the instance of the class. With this keyword, you can access the attributes and methods of the class in python. It binds the attributes with the given arguments. self is used in different places and often thought to be a keyword. But unlike in C++, self is not a keyword in Python.

### **Ques.  What is __init__ Method?**
**__init__** is a contructor method in Python and is automatically called to allocate memory when a new object/instance is created. All classes have a __init__ method associated with them. It helps in distinguishing methods and attributes of a class from local variables.

```python
class Student:
   def __init__(self, fname, lname, age, section):
       self.firstname = fname
       self.lastname = lname
       self.age = age
       self.section = section
# creating a new object
stu1 = Student("Sara", "Ansh", 22, "A2")
```

### **Ques. What is pass in Python?**
* The pass keyword represents a null operation in Python.<br> Without the pass statement in the following code, we may run into some errors during code execution.
```python
def myEmptyFunc():
   # do nothing
   pass
myEmptyFunc()    # nothing happens
## Without the pass keyword
# File "<stdin>", line 3
# IndentationError: expected an indented block
```

### **Ques. What is break, continue and pass in Python?**
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


### **Ques. What is the super() Function?**
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

### Ques. What is issubclass()?
* we can use Python built-in function issubclass(). This function returns True if the given class is the subclass of the specified class. Otherwise, it returns False.
```python
Syntex:- issubclass(class, classinfo)
```


### **Ques. What is __str__ and __repr__?**
* The repr() method returns a string containing a printable representation of an object. The repr() function calls the underlying __repr__() function of the object.
* The <b>__str__</b> method returns a string representation of an object that is human-readable while the 
* <b>__repr__</b> method returns a string representation of an object that is machine-readable.
	


### **Ques. What is Abstract Method?**
* To define an abstract **method** we use the **@abstractmethod** decorator of the abc module.
```python
from abc import ABC, abstractmethod
class DemoAbstractClass(ABC):
	@abstractmethod
	def abstract_method_name(self):
    	Pass
```

### **Ques. What is Concrete Method?**
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