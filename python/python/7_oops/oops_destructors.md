### Ques. What is Destructors?
* Destructor is a special method that is called when an object is deleted or destroyed.
* The special method **_ _del__()** is used to define a destructor. For example, when we execute del object_name destructor gets called automatically and the object gets garbage collected.
```python
class Student:

    # constructor
    def __init__(self, name):
        self.name = name
        print('Object is created')

    def show(self):
        print('Hello, my name is', self.name)

    # destructor
    def __del__(self):
        print('Object is being destroyed')

# create object
s1 = Student('Emma')    # call init method automatically
s1.show()

# delete object
del s1          # # call del method automatically

Output:-
Object is created
Hello, my name is Emma
Object is being destroyed
```