### Step 1:-
* creaet virtual enviroment 
* type cammand in cmd
```python
python -m venv env_crud
```
* For activate
```python
source env_crud/Scripts/activate
```
```pyhton
cd virtual-name\Scripts
d:\mohit\virtual-name\Scripts> activate
```

### Step 2:-
* we have install two packages/library **fastapi** and **uvicorn**
```python
pip install fastapi

# You will also need an ASGI server, for production such as Uvicorn or Hypercorn.
pip install "uvicorn[standard]"
```

### Create a file main.py with:
```python
from typing import Union
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def first_page_function():
    return {"msg":"Hello FastAPI🚀"}

@app.get("/first_page")
def first_page_function():
    return "Hello my first page url"

@app.get("/item/{id}")
def pathFunction(id):
    return {"get return id": id}

@app.get("/query")
def queryFunction(name:str, roll_no:int):
    var_name = {"name": name , "roll number":roll_no}
    return (var_name)

@app.get("/query-optional-parameter")
def queryFunction(name:str, roll_no: Union[int, None]=None):
    var_name = {"name": name , "roll number":roll_no}
    return (var_name)
```

```python
# add
from enum import Enum

class choice_names(str,Enum):
    one="one"
    two="two"
    three="three"

@app.get("/choice-function/{model_name}")
async def choiceFunction(model_name:choice_names):
    if model_name.value == "one":
        return {"model name": model_name, "message":"this is a one"}
    if model_name.value == "two":
        return {"model name": model_name, "message":"this is a two"}
    if model_name.value == "three":
        return {"model name": model_name, "message":"this is a three"}
    return model_name
```

```python
from pydantic import BaseModel

class student_details(BaseModel):
    name:str
    Class:str
    roll_no:int

@app.post("/create-student")
async def createStudent(studentDetails:student_details):
    return studentDetails
```



### Run the server with:
```python
uvicorn main:app --reload

uvicorn main:app --host 127.8.4.8 --port 12   # Difrent port

# INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
# INFO:     Started reloader process [28720]
# INFO:     Started server process [28722]
# INFO:     Waiting for application startup.
# INFO:     Application startup complete.
```
```python
Open your browser at http://127.0.0.1:8000/
Open your browser at http://127.0.0.1:8000/items
```



### Project setup one pc to another Pc.
* First of all we run the command
```python
pip freeze > requirements.txt
```
* And other system follows these step
```python
# Create and activate virtual environment
virtualenv -p python3 env
. ./env/bin/activate

# Install Python dependencies
pip install -r requirements.txt

# Create SQLite databse, run migrations
cd myapp
./manage.py migrate

# Run Django dev server
./manage.py runserver
```