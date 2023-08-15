### **Ques. Add Dictionary Items?**
```python
# Adding Items
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
thisdict["color"] = "red"
print(thisdict)

Output:- {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
```
* Adding Items using **Update()** Method.
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
thisdict.update({"color": "red"})

print(thisdict)

Output:- {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
```