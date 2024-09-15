### **Ques. What is Abstract Class?**
* We cannot create an abstract class in Python directly. However, Python does provide a module that allows us to define abstract classes. The module we can use to create an abstract class in Python is abc(abstract base class) module.
**Rule**
* PVM can not create objects of an abstract class (abstract class ka hum object nahi bna sakte hai).
* It is not neccessary to declare all methods abstract in a abstract class.
* Abstract class can have abstract method and concreate method.
* If there is any abstract method in a class, that class must be abstract.
* The abstract methods of an abstract class must be defined in its child class/subclass.

### **Ques. When use abstratc class?**
* We use abstract class when there are some common feature shered by all the objects as they are.
**Example:-**
```python
# gun is common features
# Defence Forse
#   Gun:- Ak 47
#   Area:- --
--------------------------
#   army:- Gun Ak 47,    Area:- Land
#   Air Force:- Gun Ak 47,    Area:- Sky
#   Navy:-      Gun Ak 47,    Area:- Sea
```

```python
from abc import ABC
class <Abstract_Class_Name>(ABC):
```
```python
from abc import ABC, abstractmethod
class Father(ABC):
    @abstractmethod
    def disp(self):
        pass

    def show(self):
        print("concreate class")

class child(Father):
    def disp(self):
        print("child class")
        print("defining abstrat class")
c = child()
c.disp()
c.show()
```