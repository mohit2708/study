### install package
```pthon
pip install python-dotenv
```
* Creaet the file **.env** file and 
* **load_dotenv** function from the dotenv package to load the variables from the `.env` file into the system’s environment. 
* After loading the .env file, the code retrieves specific environment variables such as “DB_URL”, “SECRET_KEY”, and “DEBUG” using the **os.getenv** function.

### create .env file
```pyhton
PROJECT_NAME    = "Mohit API's. 🔥"
PROJECT_VERSION = "1.0.0"
```

```python
from fastapi import FastAPI
import os
from dotenv import load_dotenv

app = FastAPI()

# Load .env file
load_dotenv()

DB_URL = os.getenv("DB_URL")
SECRET_KEY = os.getenv("SECRET_KEY")
DEBUG = os.getenv("DEBUG") == "True"
```

```python
from fastapi import FastAPI
import os
from dotenv import load_dotenv
from pathlib import Path

# load_dotenv()
env_path = Path('.') / '.env'
load_dotenv(dotenv_path=env_path)

# app = FastAPI()
app = FastAPI(title=os.getenv("PROJECT_NAME"),version=os.getenv("PROJECT_VERSION"))

@app.get("/")
def first_page_function():
    return {"message": f"Hello, welcome to!"}
```