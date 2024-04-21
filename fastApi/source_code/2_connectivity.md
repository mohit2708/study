### Connectivity from mysql
* install sqlalchemy -> sql orm hai
```python
pip install sqlalchemy
```
* install PyMySQL
```python
pip install PyMySQL
```

### Alembic for Database Migrations
* install Alembic
```python
pip install alembic
```
* Create Alembic Configuration File
```python
alembic init alembic
```
* This will create a directory named **alembic** in **your project directory** with a configuration file named **alembic.ini**.
* Open the alembic.ini file and configure the sqlalchemy.url parameter to point to your database connection URI.
* Create a Migration Script: 
```python
alembic revision --autogenerate -m "create_table"
```

