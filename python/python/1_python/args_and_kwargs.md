|  No.  | Python Other Questions                                                                                  |
| :---: | ------------------------------------------------------------------------------------------------------- |
|       | [What is *args and **kwargs in Python?](#ques-what-do-args-and-kwargs)                                  |
|       | [What do *(single asterisk) and **(double asterisk)](#ques-what-do-single-asterisk-and-double-asterisk) |
|       | [Positional (non-keyword) arguments](#positional-non-keyword-arguments)                                 |
|       | [Why use *args and **kwargs in Python?](#why-use-args-and-kwargs-in-python)                             |
|       | [Difference between *args and **kwargs in Python?](#difference-between-args-and-kwargs-in-python)       |
|       | [Keyword arguments](#keyword-arguments)                                                                 |
|       | [Arbitrary Arguments](#arbitrary-arguments)                                                             |

### Ques. What do *(single asterisk) and **(double asterisk)?
### Ques. What do *args and **kwargs?
* In Python, *args and **kwargs are used to allow functions to accept an arbitrary(Multipal) number of arguments.
* There are two special symbols:
1. *args (Non Keyword Arguments)
2. **kwargs (Keyword Arguments)

### Python *args/Single Asterisk
* The special syntax *args in function definitions is used to pass a variable number of arguments to a function. It is used to pass a non-keyworded, variable-length argument list.
* Single Asterisk allows the developer to pass a variable number of Positional parameters and automatically converts the input values in the form of tuples. At the same time.
```python
# Example 1
def print_colors(*args):
    print(args)
print_colors('red','blue','green','yellow')

Output:- ('red', 'blue', 'green', 'yellow')

# Example 2
def myFun(*argv):
    for arg in argv:
        print(arg)


myFun('Hello', 'Welcome', 'to', 'GeeksforGeeks')

Output:-
Hello
Welcome
to
GeeksforGeeks

# Example 3
def fun(arg1, *argv):
    print("First argument :", arg1)
    for arg in argv:
        print("Argument *argv :", arg)


fun('Hello', 'Welcome', 'to', 'GeeksforGeeks')

Output:-
First argument : Hello
Argument *argv : Welcome
Argument *argv : to
Argument *argv : GeeksforGeeks
```

### Python **kwargs/Double Asterisks
* The special syntax **kwargs in function definitions is used to pass a variable length argument list. We use the name kwargs with the double star **.
* Double Asterisk allows the users to pass a variable number of Keyword parameters in the form of a Dictionary. 
```python
# Example 1
def print_numbers(**kwargs):
  for key, value in kwargs.items():
      print (f"{key} is a {value}")
print_numbers(mohit="TL", two="two",three=3,four="four")

Output:-
mohit is a TL
two is a two
three is a 3
four is a four

# Example 2
def fun(arg1, **kwargs):
    for k, val in kwargs.items():
        print("%s == %s" % (k, val))


# Driver code
fun("Hi", s1='Geeks', s2='for', s3='Geeks')

Output:-
s1 == Geeks
s2 == for
s3 == Geeks
```

### Using both *args and **kwargs
```python
def fun(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

fun(1, 2, 3, a=4, b=5)
Output:-
Positional arguments: (1, 2, 3)
Keyword arguments: {'a': 4, 'b': 5}
```

### Why use *args and **kwargs in Python?
* *args and **kwargs allow functions to accept a variable number of arguments:
  *  *args (arguments) allows you to pass a variable number of positional arguments to a function.
  *  **kwargs (keyword arguments) allows you to pass a variable number of keyword arguments (key-value pairs) to a function.

### Difference between *args and **kwargs in Python?
* *args collects additional positional arguments as a tuple, while **kwargs collects additional keyword arguments as a dictionary.
```python
def example_function(*args, **kwargs):
    print(args)    # tuple of positional arguments
    print(kwargs)  # dictionary of keyword arguments

example_function(1, 2, 3, name='Alice', age=30)
Output:
(1, 2, 3)
{'name': 'Alice', 'age': 30}
```

### Positional (non-keyword) arguments: 
* These are the most common type of arguments. Their position in the function call determines which parameter they correspond to.
```python
def greet(name, greeting):
    print(f"{greeting}, {name}!")

greet("Alice", "Hello") # "Hello, Alice!"
```

### Keyword arguments: 
* These arguments are **passed with the parameter name** explicitly specified. This allows you to pass arguments in any order and makes the code more readable.
```python
def greet(name, greeting):
    print(f"{greeting}, {name}!")

greet(greeting="Hi", name="Bob") # "Hi, Bob!"
```

### Arbitrary Arguments:
* If you do not know how many arguments will be passed to your function, add a * before the parameter name in the function definition. This way the function will receive a tuple of arguments, and can access the items accordingly.
```python
def my_function(*kids):
    print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus") # output The youngest child is Linus
```
* If you do not know how many keyword arguments that will be passed to your function, add two asterisk: ** before the parameter name in the function definition. This way the function will receive a dictionary of arguments, and can access the items accordingly.
```python
def my_function(**kid):
    print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes") # output His last name is Refsnes
```