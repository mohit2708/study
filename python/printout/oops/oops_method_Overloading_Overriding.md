### Ques. What is Method Overloading?
* Two or more methods have the same name but different numbers of parameters, These methods are called overloaded methods.
```python
class Addition:
	# first sum for 2 params
	def my_sum(self, a, b):
		return a + b
	
	# second overloaded sum for 3 params
	def my_sum(self, a, b, c):
		return a + b + c

obj = Addition()
# print(obj.my_sum(3, 4))
print(obj.my_sum(3, 4, 5))

Output: 12
```

### Ques. What is Method Overriding?
* When a child class method has the same name, same parameters, and same return type as a method.
```python
class Vehicle:
    def max_speed(self):
        print("max speed is 100 Km/Hour")

class Car(Vehicle):
    # overridden the implementation of Vehicle class
    def max_speed(self):
        print("max speed is 200 Km/Hour")

# Creating object of Car class
car = Car()
car.max_speed()

Output:- max speed is 200 Km/Hour
```