### Create virtual enviroment
```python
python -m venv virtual-name
```

### **Activated virtual enviroment**
```pyhton
cd virtual-name\Scripts
d:\mohit\virtual-name\Scripts> activate
```

### Install django
```python
<virtual-name> d:\mohit> python -m pip install django
OR
pip install django
```

### Create project
```python
django-admin startproject projectName .
```

### Create App
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
    '<app_name>',               # add app
]

====project ki settings.py mai template add kar denge======
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['templates'],      # add
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

### Migrate file in database
```python
 python manage.py migrate
```