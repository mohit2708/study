### Create Seeder
* Create folder seeder->seed_roles.py
```python
# Main.py file
from database.models.role import Role
from database.seeders.seed_roles import seed_roles
from typing import Generator

def get_db() -> Generator:   #new
    try:
        db = SessionLocal()
        yield db
    finally:
        db.close()
```
```python
# Main.py file
@app.on_event("startup")
def add_seed_roles():
    db = SessionLocal()
    seed_roles(db)
```

* seed_roles.py file
```python
# seed_roles.py file as upsert
from database.models.role import Role
from sqlalchemy.orm import Session

def seed_roles(db: Session):
    roles = [
        {"id": 1, "name": "Admin"},
        {"id": 2, "name": "User"},
        {"id": 3, "name": "User2"},
        {"id": 4, "name": "User1"},
        # Add more roles as needed
    ]
    for role_data in roles:
        role = Role(**role_data)
        db.merge(role)  # Perform upsert (insert or update)
    db.commit()        
```
```python
# seed_roles.py file as data delete then insert
def seed_roles(db):
    # Delete existing records
    db.query(Role).delete()
    db.commit()

    # Insert new data
    roles = [
        {"id": 1, "name": "Admin"},
        {"id": 2, "name": "User"},
        # Add more roles as needed
    ]
    for role_data in roles:
        role = Role(**role_data)
        db.add(role)
    db.commit()       
```

### Run command
```python
Run the project 
```


