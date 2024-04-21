

## Database
### Config.py
* **install sqlalchemy** -> sql orm hai
```python
pip install sqlalchemy
```
* **install PyMySQL**
```python
pip install PyMySQL
```

```python
import os
from sqlalchemy import create_engine
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker
from typing import Generator

from dotenv import load_dotenv
from pathlib import Path

env_path = Path('.') / '.env'
load_dotenv(dotenv_path=env_path)



MY_SQL_USER     = os.getenv("MY_SQL_USER")
MY_SQL_SERVER   = os.getenv("MY_SQL_SERVER")
MY_SQL_PASSWORD = os.getenv("MY_SQL_PASSWORD")
MY_SQL_PORT     = os.getenv("MY_SQL_PORT")
MY_SQL_DATABASE = os.getenv("MY_SQL_DATABASE")

SQLALCHEMY_DATABASE_URL = "mysql+pymysql://root:@localhost/fastapi_crud"
# SQLALCHEMY_DATABASE_URL = "mysql+pymysql://{MY_SQL_USER}:@{MY_SQL_SERVER}/{MY_SQL_DATABASE}"

print(SQLALCHEMY_DATABASE_URL)

engine = create_engine(SQLALCHEMY_DATABASE_URL)
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

Base = declarative_base()

def get_db() -> Generator:   #new
    try:
        db = SessionLocal()
        yield db
    finally:
        db.close()
```

### Database > schemas > user.py
#### Create email validation
* insatll package for **duplicate email** exist
```python
pip install pydantic[email]
```

```python
# Database > schemas > user.py
from pydantic import BaseModel, EmailStr, Field

class UserCreate(BaseModel):
    first_name: str = Field(..., min_length=1, max_length=255, description="The first name of the user")
    last_name: str = Field(..., min_length=1, max_length=255, description="The last name of the user")
    email: EmailStr = Field(..., description="The email address of the user")
    password: str = Field(..., min_length=1, description="The password of the user")
```


