### **Ques. What is MRO(Method Resolution Order) / Diamond Problam?**
* MRO is a concept used in inheritance.
* If a class is derived from more then one class, then it is called multiple inheritance.
* In Python, the MRO is from bottom to top and left to right. This means that, first, the method is searched in the class of the object. If it’s not found, it is searched in the immediate super class. In the case of multiple super classes, it is searched left to right, in the order by which was declared by the developer.

```python
class father():
    def showF(self):
        print("fathe class method")

class mother():
    def showM(self):
        print("mother class method")
class son(father, mother):
    def showS(self):
        print("son class method")

obj = son()
obj.showS()
obj.showF()
obj.showM()

Output:-
son class method
fathe class method
mother class method
------------------------------------------------------------------

# Example:-
class father():
    def display(self):
        print("father class method")

class mother():
    def display(self):
        print("mother class method")
        
        
class son(mother,father):                  # left to right 
    def showS(self):
        print("son class method")

obj = son()
obj.display()

Output:-
mother class method

++++++++++++++++++++
class son(father, mother):                  # left to right 
    def showS(self):
        print("son class method")

obj = son()
obj.display()

Output:- father class method
-------------------------------------------------------------------------
# Using Constructor
class father():
    def __init__(self):
        super().__init__()      # Calling Parent Class Constructor
        print("father class Constructor")
    def showF(self):
        print("father class method")

class mother():
    def __init__(self):
        super().__init__()      # Calling Parent Class Constructor
        print("mother class Constructor")
    def showM(self):
        print("mother class method")
class son(father, mother):                  # left to right 
    def __init__(self):
        super().__init__()      # Calling Parent Class Constructor 1st Wala
        print("son class Constructor")
    def showS(self):
        print("son class method")

obj = son()

Output:-
mother class Constructor
father class Constructor
son class Constructor
```