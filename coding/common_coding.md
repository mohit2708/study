#### **Create virtual enviroment**
* create the folder and open the cmd
```python
python -m venv virtual-name
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
    '<app_name>',
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

### **Migrate file in database**
```python
 python manage.py migrate
```

### **Super user create**
```python
(env) blog_project> python manage.py createsuperuser
user
email
pass
```

### **Show the table in admin.py**
```python
from django.contrib import admin
from store.models.product import Product

# Register your models here.

@admin.register(Product)
class ProductModelAdmin(admin.ModelAdmin):
	list_display = ['name', 'price']
	list_editable = ['price']				# Field Editable in the admin pannel.
	search_fields = ('price',)				# Serach field option in admin pannel
	list_filter = ('name','price')	# list filter in admin pannel
 
# admin.site.register(Product,ProductModelAdmin) 		# instead of @admin.register(Product)
```

```python
python manage.py migrate --run-syncdb
```


### **urls setting**
```python
======project urls.py=====
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('authentication.urls')),
]
=========crete urls.py file in your app======
from django.contrib import admin
from django.urls import path
from . import views

urlpatterns = [
	path('', views.home, name='home'),
]
```

### **In view.py file**
```python
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.
def home(request):
	return HttpResponse('first page')
```

### **View calling using template**
```python
====setting.py=========
 'DIRS': ['templates'],

=======create template folder in root directiry where is managed file=====
=======and create file index.html ================
<h1>Hello</h1>
<h1>Hello {{name}}</h1>


=====views.py=======
from django.shortcuts import render
from django.http import HttpResponse
def individual_post(request):
    return render(request, 'index.html')
    return render(request,"signup.html", {'name':'mohit'})
```

### **Ek page ko dusre mai call karana**
```python
==========base.html===========
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
</head>
<body>
 {% block start %}
 {% endblock %}
</body>
</html>
===========home.html===========
{% extends "base.html" %}
{% block start %}
kuch bhi
{% endblock start %}
```






