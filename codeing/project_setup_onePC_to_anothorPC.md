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




pip install -r requirements.txt
You can also use pip freeze to get an exact snapshot of your current Python packages and write them to a file:

pip freeze > requirements.txt