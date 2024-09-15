### Ques. What is Destructors?
* Destructor is a special method that is called when an object is deleted or destroyed.
* The special method **_ _del__()** is used to define a destructor. For example, when we execute del object_name destructor gets called automatically and the object gets garbage collected.
```python
class Student:

    # constructor
    def __init__(self, name):
        print('Inside Constructor')
        self.name = name
        print('Object initialized')

    def show(self):
        print('Hello, my name is', self.name)

    # destructor
    def __del__(self):
        print('Inside destructor')
        print('Object destroyed')

# create object
s1 = Student('Emma')
s1.show()

# delete object
del s1

Output:-
Inside Constructor
Object initialized

Hello, my name is Emma

Inside destructor
Object destroyed
```