### What is static method?
* static method don't use the self parameter.
* static method ko hum object ke sath bhi call kar sakte hai or class ke stah bhi.
```python
class Student:
    
    @staticmethod
    def hello():
        print("hello")
    
stu1 = Student()
stu1.hello()        # output:- Hello  
Student.hello()     # output:- Hello
```