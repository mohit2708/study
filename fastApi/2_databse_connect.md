### Connect database
* Install sqlalchemy
```python
pip install sqlalchemy
```
* create database.py file in same directory
```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker, Session
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.ext.asyncio import AsyncSession

SQLITEADATABASE_URL = "sqlite:///./sqllite_app.db"
MYSQLDATABASE_URL = "mysql://root:@localhost/fastapi"   # mysql://username:password@host/tablename

engine = create_engine(SQLITEADATABASE_URL, connect_args={"check_same_thread":False})  # its line only, jab sqllite se connectivity ho.
engine = create_engine(SQLITEADATABASE_URL)

# Regular synchronous session
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

Base = declarative_base()
```