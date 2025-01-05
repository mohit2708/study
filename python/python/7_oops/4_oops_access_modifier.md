|  No.  | [Access Modifiers]()                                             |
| :---: | ---------------------------------------------------------------- |
|       | [Python Access Modifiers?](#python-access-modifiers)             |
|       | [private attributes and method?](#private-attributes-and-method) |

### Python Access Modifiers
* **Public Member:** Accessible anywhere from outside the class.
* **Private Member:** private attributes and method Accessible only within the class.
* **Protected Member:** Accessible within the class and it's sub-classes.
```python
#defining class Student
class Student:
    #constructor is defined
    def __init__(self, name, age, salary):
        self.age = age             # public Attribute
        self._name = name          # protected Attribute 
        self.__salary = salary     # private Attribute

    def _funName(self):            # protected method
        pass
 
    def __funName(self):           # private method
        pass

# object creation
obj = Student('Mohit',53434)
```

* **Public Access Modifier**
* By default, all the variables and member functions of a class are public in a python program.
```python
class Employee:
    # constructor
    def __init__(self, name, sal):
        self.name = name;
        self.sal = sal;
obj = Employee('mohit',555)
print(obj.name)
print(obj.sal)

Output:- 
Mohit
555
```

* **protected Access Modifier:-** Accessible within the class and it's sub-classes.
* adding a prefix _(single underscore) to a variable name makes it protected.
```python
class Employee:
    # constructor
    def __init__(self, name, sal):
        self._name = name;   # protected attribute 
        self._sal = sal;     # protected attribute

obj = Employee('mohit',15)
print(obj._name)

Output:-
Mohit

# Example2:-
class Employee:
    # constructor
    def __init__(self, name, sal):
        self._name = name;   # protected attribute 
        self._sal = sal;     # protected attribute
 
class HR(Employee):
    def task(self):
        print ("We manage Employees")
        

hrEmp = HR("Captain", 10000);
print(hrEmp._sal)
print(hrEmp.task())

Output:-
10000
We manage Employees
```

*  **private Access Modifier**
* While the addition of prefix __(double underscore) results in a member variable or function becoming private.
* jab hame privete attribute ko call karna ho to ek function usi class mai banakar print kar sakte hai.
* Example for private attribute
```python
class Account:
    def __init__(self,acc_no, acc_pass):
        self.acc_no = acc_no
        self.__acc_pass = acc_pass
        
    def reset_pass(self):
        print(self.__acc_pass)

acc1 = Account("2582123", "pass@123")
print(acc1.reset_pass())    # Output:- pass@123
```

### private attributes and method?
* Private attributes & method are meant to be used only within the class and are not accessibale from the outside the class.
* Example for private method
* agar humne double underscore se kisi ko private kar diya hai to use usi class ke function call kar payenge.
* ham diractly hello function ko call nahi kar sakte hai kyuki hello function private hai agar hame karana hai to usi class mai dusra function banakar welcome banakar usme call karenge phir welcome function ko call karenge to call ho jayega.

#### private method
```python
class Person:
   
    def __hello(self):
        print("calling hello function")
    
    def welcome(self):
        self.__hello()
    
p1 = Person()
print(p1.welcome())

Output:-
calling hello function
```

```python
class Person:
    def __init__(self, name, age, height):
        self.name     = name   # public
        self._age     = age    # protected
        self.__height = height # private

p1 = Person("John", 20, 170)

print(p1.name)        # public: can be accessed
print(p1._age)        # protected: can be accessed but not advised
# print(p1.__height)  # private: will give AttributeError
```
#### private attributes
```python
class Person:
    __name = "mohit saxena"

    def result(self):
        print(self.__name)

p1 = Person()
print(p1.__name)       # error aayegi
p1.result()            # ab error nahi aayegi
```