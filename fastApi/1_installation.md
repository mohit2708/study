#### **Create virtual enviroment**
* create the folder and open the cmd
```python
python -m venv virtual-name
OR
pip install virtualenv  # Install the package.
virtualenv MyFirstApp
MyFirstApp\scripts\activate
```

#### **Activated virtual enviroment**
```pyhton
cd virtual-name\Scripts
d:\mohit\virtual-name\Scripts> activate
```

### install fastapi
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
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q": q}
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

### FastApi Templates
```python
pip install jinja2
```

* add some important librariry
```python
# Main.py
from fastapi import FastAPI, Request
from fastapi.responses import HTMLResponse
from fastapi.staticfiles import StaticFiles
from fastapi.templating import Jinja2Templates

```