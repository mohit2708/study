### Try, Except, else and Finally
* The try...except block is used to handle exceptions in Python.
* Try: This block will test the excepted error to occur
* Except:  Here you can handle the error
* Else: If there is no exception then this block will be executed
* Finally: Finally block always gets executed either exception is generated or not
```python
try:
       # Some Code.... 
except:
       # optional block
       # Handling of exception (if required)
else:
       # execute if no exception
finally:
      # Some code .....(always executed)
```
* Catch Multiple Exceptions in Python
```python
try:
    x = int(input("Enter a number: "))
    result = 10 / x
except ZeroDivisionError:
    print("You cannot divide by zero.")
except ValueError:
    print("Invalid input. Please enter a valid number.")
except Exception as e:
    print(f"An error occurred: {e}")
```
* Catching Specific Exceptions in Python
```python
try:
    
    even_numbers = [2,4,6,8]
    print(even_numbers[5])

except ZeroDivisionError:
    print("Denominator cannot be 0.")
    
except IndexError:
    print("Index Out of Bound.")

# Output: Index Out of Bound
```
* Python try with else clause
```python
# program to print the reciprocal of even numbers

try:
    num = int(input("Enter a number: "))
    assert num % 2 == 0
except:
    print("Not an even number!")
else:
    reciprocal = 1/num
    print(reciprocal)

Output:-
Enter a number: 1
Not an even number!

Output:-
Enter a number: 4
0.25

Output:-
Enter a number: 0
Traceback (most recent call last):
  File "<string>", line 7, in <module>
    reciprocal = 1/num
ZeroDivisionError: division by zero
```
* Python try...finally
```python
try:
    numerator = 10
    denominator = 0

    result = numerator/denominator

    print(result)
except:
    print("Error: Denominator cannot be 0.")
    
finally:
    print("This is finally block.")

Output:-
Error: Denominator cannot be 0.
This is finally block.
```