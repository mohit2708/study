### Install alembic
* install package
```python
pip install alembic
```
* Initialize Alembic:
```python
alembic init alembic
```

### Genrate alembic
```python
alembic revision --autogenerate -m "create user and blog table migrations"  #analyzes tables and creates a migration file
```
```python
alembic upgrade head  #executes the migration files to make actual changes in db
```
