### **Ques.  What is Polymorphism?**
* When one task is performed by different ways i.e known as polymorphism.
* A child class inherits all the methods from the parent class.
* we understand that one task can be performed in different ways. 
* Polymorphism is ability to use function & method in different ways.

**Types of Polymorphism?**
* Polymorphism could be static and dynamic both. Overloading is static polymorphism while, overriding is dynamic polymorphism.
1. **Duck Typing**
2. **Compile time polymorphism (Static) - Method Overloading:-** Overloading is defining functions/methods that have same signatures with different parameters in the same class.
```python
class VIP:
    def vsp(self, x=None, y=None):
        if x==None and y==None:
            print("this is python polymorphism")
        elif x!=None and y==None:
            f=1
            for i in range(1, x+1):
                f= f*i
            print(f)
        else:
            print("add:",x+y)

obj = VIP()

obj.vsp()
obj.vsp(5)
obj.vsp(5,5)

output:-
this is python polymorphism
120
add: 10
```
3. **Runtime time polymorphism (Dynamic) - Method Overriding:-** 
   1. Overriding is redefining parent class functions/methods in child class with same signature. So, basically the purpose of overriding is to change the behavior of your parent class method.
   2. function wo wala call hota jiska hamne obj banya hota hai.
```python
class A:
    def vsp(self):
        print("Hiiiiii")
class B(A):
    def vsp(self):
        print("Hello")

obj = A()
obj.vsp()

Output:-
Hiiiiii
```

4. **operator Overloading**
```python
class A:
    def vsp(self,x):
        self.x = x
    def __add__(self,o):
        return self.x+o.x
    
obj1 = A()
obj1.vsp(10)

obj2 = A()
obj2.vsp(20)

print(obj1+obj2)

Output:- 30
```

**Polymorphism with Class Methods**
```python
class Monkey:
    def color(self):
        print("The monkey is yellow coloured!")

    def eats(self):
        print("The monkey eats bananas!")


class Rabbit:
    def color(self):
        print("The rabbit is white coloured!")

    def eats(self):
        print("The rabbit eats carrots!")


mon = Monkey()
rab = Rabbit()
for animal in (mon, rab):
    animal.color()
    animal.eats()

Output:-
The monkey is yellow coloured!
The monkey eats bananas!
The rabbit is white coloured!
The rabbit eats carrots!
```
**Polymorphism with Inheritance**
```python
class Bird:
  def intro(self):
    print("There are many types of birds.")
     
  def flight(self):
    print("Most of the birds can fly but some cannot.")
   
class sparrow(Bird):
  def flight(self):
    print("Sparrows can fly.")
     
class ostrich(Bird):
  def flight(self):
    print("Ostriches cannot fly.")
     
obj_bird = Bird()
obj_spr = sparrow()
obj_ost = ostrich()
 
obj_bird.intro()
obj_bird.flight()
 
obj_spr.intro()
obj_spr.flight()
 
obj_ost.intro()
obj_ost.flight()

Output:-
There are many types of birds.
Most of the birds can fly but some cannot.
There are many types of birds.
Sparrows can fly.
There are many types of birds.
Ostriches cannot fly.
```