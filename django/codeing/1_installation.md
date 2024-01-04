### Install Python
* Install Python https://www.python.org/downloads/
* python check version --> python --version/py -V
* Check pip version --> pip --version

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

#### **Install django**
```python
<virtual-name> d:\mohit> python -m pip install django
OR
pip install django
```

#### **Uninstall django**
```python
pip uninstall django
```

#### **Check django version**
```python
django-admin --version (OR)
python -m django --version
```

#### **Create project**
```python
django-admin startproject projectName .
OR
python manage.py startproject projectName .
```
#### **Start server**
```python
python manage.py runserver
# change port
python manage.py runserver 8484
```

#### **Create App**
```python

python manage.py startapp app_name
OR
django-admin startapp app_name

====project ki settings.py mai appn_ame add kar denge======
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app_name',
]

====project ki settings.py mai template add kar denge======
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```

### MySQL Database Connectivity
```python
firstly we create the database in mysql
```
* Install the package:- 
```python
pip install mysqlclient 
```
In setting.py
```python
Update the connection string.
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'database_name',
        'USER': 'mysql_user',
        'PASSWORD': 'mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
        'OPTIONS': {
            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'"
            
         }
    }
}
```
```python
python manage.py migrate
```