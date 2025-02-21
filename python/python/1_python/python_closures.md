### Python Closures
* Python closure is a nested function that allows us to access variables of the outer function even after the outer function is closed.
* function ke ander ke function ko nested function kahte hai.
```python
def functionA():
   print ("Outer function")
   def functionB():
      print ("Inner function")
   functionB()

functionA()

Output:
Outer function
Inner function
```
```python
def functionA(name):
   print ("Outer function")
   def functionB():
      print ("Inner function")
      print ("Hi {}".format(name))
   functionB()
   
functionA("Python")

Output:-
Outer function
Inner function
Hi Python
```
```python
def greet(name):
    # inner function
    def display_name():
        print("Hi", name)
    
    # call inner function
    display_name()

# call outer function
greet("John")  

# Output: Hi John
```