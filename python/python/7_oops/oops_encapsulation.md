### **Ques.  What is Encapsulation?**
* Binding(or wrapping) code and data together into a single unit is known as encapsulation. One object is encapsulated from another object.

```python
class BankAccount:
        self.__account_number = account_number  # Private attribute (using double underscore)
        self.__balance = balance  # Private attribute

    # Public method to access private balance
    def get_balance(self):
        return self.__balance

    # Public method to modify balance with validation
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            return True
        return False

    # Public method to withdraw with validation
    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount
            return True
        return False


# Creating an instance of the BankAccount
account = BankAccount("123456", 1000)

# Using public methods to interact with private attributes
print(account.get_balance())  # 1000
account.deposit(500)
print(account.get_balance())  # 1500
account.withdraw(200)
print(account.get_balance())  # 1300
```

**Code of getter & setter in Encapsulation**
```python
class Library:
    def __init__(self, id, name):
        self.bookId = id
        self.bookName = name
        
    def setBookName(self, newBookName): #setters method to set the book name
        self.bookName = newBookName
        
    def getBookName(self): #getters method to get the book name
        print(f"The name of book is {self.bookName}")

        
book = Library(101,"Hindi")
book.getBookName()
book.setBookName("English")
book.getBookName()

Output:-
The name of book is Hindi
The name of book is English
```