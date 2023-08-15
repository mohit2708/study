### **Ques. Access Item of Dictionary?**
* You can access the items of a dictionary by referring to its **key name**, inside square brackets.
```python
thisdict =	{
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
x = thisdict["model"]
print(x)

Output:- Mustang
```
* Using the **get()** Method
```python
thisdict =	{
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
}
x = thisdict.get("model")
print(x)

Output:- Mustang
```
* Get <b>All Keys</b> of the Dictionary:- The **keys() method** will return a list of all the keys in the dictionary.
```python
car = {
"brand": "Ford",
"model": "Mustang",
"year": 1964
}

x = car.keys()
print(x)

Output:- dict_keys(['brand', 'model', 'year'])
```
* Get <b>All Values</b> of the Dictionary and We can change the value of a specific item by referring to its key name.
```python
car = {
"brand": "Ford",
"model": "Mustang",
"year": 1964
}

x = car.values()
print(x)

Output:- dict_values(['Ford', 'Mustang', 1964])
```
* Get <b>All Items</b> :- The items() method will return each item in a dictionary, as tuples in a list.
```python
thisdict = {
   "brand": "Ford",
   "model": "Mustang",
   "year": 1964
}

x = thisdict.items()
print(x)

Output:- dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])
```

