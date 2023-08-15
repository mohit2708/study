### **Ques.  What is Encapsulation?**
* Binding(or wrapping) code and data together into a single unit is known as encapsulation. One object is encapsulated from another object.

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

        
book = Library(101,"The Witchers")
book.getBookName()
book.setBookName("The Witchers Returns")
book.getBookName()

Output:-
The name of book is The Witchers
The name of book is The Witchers Returns
```